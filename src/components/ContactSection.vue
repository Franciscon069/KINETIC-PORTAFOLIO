<script setup>
import { ref, reactive, onMounted } from 'vue'
import { useI18n } from 'vue-i18n'
import emailjs from '@emailjs/browser'

const { t } = useI18n()

// Configuración de EmailJS desde variables de entorno
const serviceId = import.meta.env.VITE_EMAILJS_SERVICE_ID
const templateId = import.meta.env.VITE_EMAILJS_TEMPLATE_ID
const publicKey = import.meta.env.VITE_EMAILJS_PUBLIC_KEY

const form = reactive({
  name: '',
  email: '',
  message: ''
})

const status = ref('idle') // idle, sending, success, error

const handleSubmit = async () => {
  if (status.value === 'sending') return
  
  status.value = 'sending'
  
  try {
    await emailjs.send(
      serviceId,
      templateId,
      {
        from_name: form.name,
        from_email: form.email,
        message: form.message,
        to_name: 'Francisco Hermosillo',
      },
      publicKey
    )

    status.value = 'success'
    // Limpiar formulario
    form.name = ''
    form.email = ''
    form.message = ''
    
    // Regresar al estado inicial tras 5 segundos
    setTimeout(() => {
      status.value = 'idle'
    }, 5000)
  } catch (error) {
    console.error('EmailJS Error:', error)
    status.value = 'error'
    
    setTimeout(() => {
      status.value = 'idle'
    }, 5000)
  }
}

onMounted(() => {
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('active');
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('#contact .reveal').forEach(el => observer.observe(el));
});
</script>

<template>
  <section id="contact" class="py-20 md:py-32 px-6 md:px-8 bg-surface overflow-hidden">
    <div class="max-w-screen-xl mx-auto grid md:grid-cols-2 gap-12 md:gap-24 items-start">
      <div class="reveal">
        <h2 class="font-headline text-4xl md:text-7xl font-bold tracking-tighter text-on-background mb-6 md:mb-8">
          {{ t('contact.title') }}
        </h2>
        <p class="text-on-surface-variant text-base md:text-xl leading-relaxed mb-10 md:mb-12 max-w-md">
          {{ t('contact.description') }}
        </p>

        <div class="space-y-4 md:space-y-6">
          <div class="flex items-center gap-4 md:gap-6 group">
            <div class="w-12 h-12 md:w-14 md:h-14 rounded-xl bg-surface-container-high flex items-center justify-center text-primary group-hover:bg-primary group-hover:text-on-primary-fixed transition-all shadow-lg shadow-primary/5">
              <span class="material-symbols-outlined">verified</span>
            </div>
            <div>
              <p class="text-[10px] text-on-surface-variant uppercase tracking-widest">{{ t('contact.statusLabel') }}</p>
              <p class="text-base md:text-lg font-bold font-headline">{{ t('contact.statusValue') }}</p>
            </div>
          </div>

          <div class="flex items-center gap-4 md:gap-6 group cursor-pointer">
            <div class="w-12 h-12 md:w-14 md:h-14 rounded-xl bg-surface-container-high flex items-center justify-center text-secondary group-hover:bg-secondary group-hover:text-on-secondary transition-all shadow-lg shadow-secondary/5">
              <span class="material-symbols-outlined">terminal</span>
            </div>
            <div>
              <p class="text-[10px] text-on-surface-variant uppercase tracking-widest">{{ t('contact.networkLabel') }}</p>
              <p class="text-base md:text-lg font-bold font-headline">{{ t('contact.network') }}</p>
            </div>
          </div>
        </div>
      </div>

      <div class="bg-surface-container-low p-6 md:p-10 rounded-3xl border border-outline-variant/10 shadow-2xl relative reveal reveal-delay-2">
        <div class="absolute top-4 right-6 flex gap-1.5 md:gap-2">
          <div class="w-1.5 h-1.5 md:w-2 md:h-2 rounded-full bg-error/40"></div>
          <div class="w-1.5 h-1.5 md:w-2 md:h-2 rounded-full bg-primary/40"></div>
          <div class="w-1.5 h-1.5 md:w-2 md:h-2 rounded-full bg-secondary/40"></div>
        </div>

        <form @submit.prevent="handleSubmit" class="space-y-6 md:space-y-8 mt-4 md:mt-6">
          <div class="grid grid-cols-1 sm:grid-cols-2 gap-6 md:gap-8">
            <div class="space-y-2">
              <label class="text-[10px] uppercase tracking-widest text-on-surface-variant font-bold">{{ t('contact.formName') }}</label>
              <input 
                v-model="form.name"
                class="w-full bg-surface-container-lowest border border-outline-variant/5 rounded-xl focus:ring-2 focus:ring-primary/20 focus:border-primary text-on-surface p-4 transition-all" 
                :placeholder="t('contact.formNamePlaceholder')" 
                type="text"
                required
              />
            </div>
            <div class="space-y-2">
              <label class="text-[10px] uppercase tracking-widest text-on-surface-variant font-bold">{{ t('contact.formEmail') }}</label>
              <input 
                v-model="form.email"
                class="w-full bg-surface-container-lowest border border-outline-variant/5 rounded-xl focus:ring-2 focus:ring-primary/20 focus:border-primary text-on-surface p-4 transition-all" 
                :placeholder="t('contact.formEmailPlaceholder')" 
                type="email"
                required
              />
            </div>
          </div>

          <div class="space-y-2">
            <label class="text-[10px] uppercase tracking-widest text-on-surface-variant font-bold">{{ t('contact.formMessage') }}</label>
            <textarea 
              v-model="form.message"
              class="w-full bg-surface-container-lowest border border-outline-variant/5 rounded-xl focus:ring-2 focus:ring-primary/20 focus:border-primary text-on-surface p-4 transition-all resize-none" 
              :placeholder="t('contact.formMessagePlaceholder')" 
              rows="4"
              required
            ></textarea>
          </div>

          <Transition name="fade">
            <div v-if="status === 'success'" class="p-4 bg-primary/10 border border-primary/20 rounded-xl text-primary text-sm flex items-center gap-3">
              <span class="material-symbols-outlined text-base">check_circle</span>
              {{ t('contact.formSuccess') }}
            </div>
          </Transition>
          
          <Transition name="fade">
            <div v-if="status === 'error'" class="p-4 bg-error/10 border border-error/20 rounded-xl text-error text-sm flex items-center gap-3">
              <span class="material-symbols-outlined text-base">error</span>
              {{ t('contact.formError') }}
            </div>
          </Transition>

          <button 
            :disabled="status === 'sending'"
            class="w-full py-4 bg-primary text-on-primary-fixed font-black uppercase tracking-[0.2em] rounded-xl hover:brightness-110 active:scale-[0.98] transition-all disabled:opacity-50 disabled:cursor-not-allowed shadow-xl shadow-primary/20" 
            type="submit"
          >
            <span v-if="status === 'sending'" class="flex items-center justify-center gap-2">
              <span class="w-4 h-4 border-2 border-on-primary-fixed border-t-transparent rounded-full animate-spin"></span>
              {{ t('contact.sending') }}
            </span>
            <span v-else>
              {{ t('contact.submit') }}
            </span>
          </button>
        </form>
      </div>
    </div>
  </section>
</template>

<style scoped>
.fade-enter-active, .fade-leave-active {
  transition: all 0.3s ease;
}
.fade-enter-from, .fade-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}
</style>
>