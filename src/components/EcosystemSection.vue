<script setup>
import { Icon } from '@iconify/vue'
import { useI18n } from 'vue-i18n'

const { t } = useI18n()

// Configuración centralizada de tecnologías para evitar repetición de código
const stack = [
  { name: 'Python', icon: 'logos:python' },
  { name: 'Java', icon: 'logos:java' },
  { name: 'JavaScript', icon: 'logos:javascript' },
  { name: 'TypeScript', icon: 'logos:typescript-icon' },
  { name: 'Laravel', icon: 'logos:laravel' },
  { name: 'SQL', icon: 'logos:mysql' },
  { name: 'Vue.js', icon: 'logos:vue' },
  { name: 'React', icon: 'logos:react' },
  { name: 'HTML 5', icon: 'logos:html-5' },
  { name: 'Tailwindcss', icon: 'logos:tailwindcss-icon' },
  { name: 'Git', icon: 'logos:git-icon' },
  { name: 'GitHub', icon: 'logos:github-icon' },
]
</script>

<template>
  <section id="ecosystem" class="py-32 px-8 bg-surface-container-low">
    <div class="max-w-screen-xl mx-auto">
      <div class="grid md:grid-cols-2 gap-16 items-start mb-24">
        <h2 class="font-headline text-4xl md:text-6xl font-bold tracking-tighter text-on-background">
          {{ t('ecosystem.title', { highlight: '' }) }}
          <span class="text-secondary">{{ t('ecosystem.highlight') }}</span>
        </h2>
      </div>

      <div class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-6 gap-px bg-outline-variant/10 rounded-xl overflow-hidden border border-outline-variant/20">
        <div 
          v-for="tech in stack" 
          :key="tech.name"
          class="bg-surface group p-8 flex flex-col items-center justify-center gap-6 hover:bg-surface-container-high transition-all duration-500 cursor-default"
        >
          <div class="w-20 h-20 rounded-2xl bg-surface-container-high flex items-center justify-center group-hover:scale-110 group-hover:rotate-3 transition-all duration-500 shadow-sm group-hover:shadow-md">
            <Icon 
              :icon="tech.icon" 
              class="text-5xl filter grayscale group-hover:grayscale-0 transition-all duration-500" 
            />
          </div>
          
          <span class="font-headline font-bold tracking-tight text-center text-on-surface/80 group-hover:text-primary transition-colors">
            {{ tech.name }}
          </span>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
/* Opcional: Añade un suavizado extra a las transiciones */
.bg-surface {
  backface-visibility: hidden;
  transform: translateZ(0);
}
</style>