<script setup>
import { useI18n } from 'vue-i18n'

const { t } = useI18n()
</script>

<template>
  <section id="contact" class="py-32 px-8 bg-surface">
    <div class="max-w-screen-xl mx-auto grid md:grid-cols-2 gap-24 items-start">
      <div>
        <h2 class="font-headline text-5xl md:text-7xl font-bold tracking-tighter text-on-background mb-8">{{ t('contact.title', { highlight: '' }) }}</h2>
        <p class="text-on-surface-variant text-xl leading-relaxed mb-12 max-w-md">
          {{ t('contact.description') }}
        </p>

        <div class="space-y-6">
          <div class="flex items-center gap-6 group cursor-pointer">
            <div class="w-14 h-14 rounded-lg bg-surface-container-high flex items-center justify-center text-primary group-hover:bg-primary group-hover:text-on-primary-fixed transition-all">
              <span class="material-symbols-outlined">alternate_email</span>
            </div>
            <div>
              <p class="text-xs text-on-surface-variant uppercase tracking-widest">{{ t('contact.emailLabel') }}</p>
              <p class="text-lg font-bold font-headline">{{ t('contact.email') }}</p>
            </div>
          </div>

          <div class="flex items-center gap-6 group cursor-pointer">
            <div class="w-14 h-14 rounded-lg bg-surface-container-high flex items-center justify-center text-secondary group-hover:bg-secondary group-hover:text-on-secondary transition-all">
              <span class="material-symbols-outlined">terminal</span>
            </div>
            <div>
              <p class="text-xs text-on-surface-variant uppercase tracking-widest">{{ t('contact.networkLabel') }}</p>
              <p class="text-lg font-bold font-headline">{{ t('contact.network') }}</p>
            </div>
          </div>
        </div>
      </div>

      <div class="bg-surface-container-low p-10 rounded-2xl border border-outline-variant/10 shadow-2xl relative">
        <div class="absolute top-4 right-6 flex gap-2">
          <div class="w-2 h-2 rounded-full bg-error/40"></div>
          <div class="w-2 h-2 rounded-full bg-primary/40"></div>
          <div class="w-2 h-2 rounded-full bg-secondary/40"></div>
        </div>

        <form action="#" class="space-y-8 mt-4">
          <div class="grid grid-cols-2 gap-8">
            <div class="space-y-2">
              <label class="text-[10px] uppercase tracking-widest text-on-surface-variant font-bold">{{ t('contact.formName') }}</label>
              <input 
                class="w-full bg-surface-container-lowest border-none rounded-lg focus:ring-1 focus:ring-primary text-on-surface p-4 transition-all" 
                :placeholder="t('contact.formNamePlaceholder')" 
                type="text"
              />
            </div>
            <div class="space-y-2">
              <label class="text-[10px] uppercase tracking-widest text-on-surface-variant font-bold">{{ t('contact.formEmail') }}</label>
              <input 
                class="w-full bg-surface-container-lowest border-none rounded-lg focus:ring-1 focus:ring-primary text-on-surface p-4 transition-all" 
                :placeholder="t('contact.formEmailPlaceholder')" 
                type="email"
              />
            </div>
          </div>

          <div class="space-y-2">
            <label class="text-[10px] uppercase tracking-widest text-on-surface-variant font-bold">{{ t('contact.formMessage') }}</label>
            <textarea 
              class="w-full bg-surface-container-lowest border-none rounded-lg focus:ring-1 focus:ring-primary text-on-surface p-4 transition-all" 
              :placeholder="t('contact.formMessagePlaceholder')" 
              rows="4"
            ></textarea>
          </div>

          <button 
            class="w-full py-4 bg-primary text-on-primary-fixed font-black uppercase tracking-[0.2em] rounded-lg hover:brightness-110 active:scale-[0.98] transition-all" 
            type="submit"
          >
            {{ t('contact.submit') }}
          </button>
        </form>
      </div>
    </div>
  </section>
</template>
