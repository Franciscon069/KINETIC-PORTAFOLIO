<script setup>
import { useI18n } from 'vue-i18n'

const { t } = useI18n()
</script>

<template>
  <section id="ecosystem" class="py-32 px-8 bg-surface-container-low">
    <div class="max-w-screen-xl mx-auto">
      <div class="grid md:grid-cols-2 gap-16 items-start mb-24">
        <h2 class="font-headline text-4xl md:text-6xl font-bold tracking-tighter text-on-background">
          {{ t('ecosystem.title', { highlight: '' }) }}<span class="text-secondary">{{ t('ecosystem.highlight') }}</span>
        </h2>
        <p class="text-on-surface-variant text-lg leading-relaxed pt-2">
          {{ t('ecosystem.description') }}
        </p>
      </div>

      <div class="grid grid-cols-2 md:grid-cols-5 gap-px bg-outline-variant/10 rounded-xl overflow-hidden">
        <div class="bg-surface group p-12 flex flex-col items-center justify-center gap-6 hover:bg-surface-container transition-all duration-500 cursor-pointer">
          <div class="w-16 h-16 rounded-full bg-surface-container-high flex items-center justify-center group-hover:scale-110 transition-transform">
            <span class="material-symbols-outlined text-4xl text-primary">layers</span>
          </div>
          <span class="font-headline font-bold text-xl tracking-tight">Vue.js</span>
        </div>

        <div class="bg-surface group p-12 flex flex-col items-center justify-center gap-6 hover:bg-surface-container transition-all duration-500 cursor-pointer">
          <div class="w-16 h-16 rounded-full bg-surface-container-high flex items-center justify-center group-hover:scale-110 transition-transform">
            <span class="material-symbols-outlined text-4xl text-secondary">animation</span>
          </div>
          <span class="font-headline font-bold text-xl tracking-tight">React</span>
        </div>

        <div class="bg-surface group p-12 flex flex-col items-center justify-center gap-6 hover:bg-surface-container transition-all duration-500 cursor-pointer">
          <div class="w-16 h-16 rounded-full bg-surface-container-high flex items-center justify-center group-hover:scale-110 transition-transform">
            <span class="material-symbols-outlined text-4xl text-primary">verified</span>
          </div>
          <span class="font-headline font-bold text-xl tracking-tight">TypeScript</span>
        </div>

        <div class="bg-surface group p-12 flex flex-col items-center justify-center gap-6 hover:bg-surface-container transition-all duration-500 cursor-pointer">
          <div class="w-16 h-16 rounded-full bg-surface-container-high flex items-center justify-center group-hover:scale-110 transition-transform">
            <span class="material-symbols-outlined text-4xl text-secondary">database</span>
          </div>
          <span class="font-headline font-bold text-xl tracking-tight">Laravel</span>
        </div>

        <div class="bg-surface group p-12 flex flex-col items-center justify-center gap-6 hover:bg-surface-container transition-all duration-500 cursor-pointer">
          <div class="w-16 h-16 rounded-full bg-surface-container-high flex items-center justify-center group-hover:scale-110 transition-transform">
            <span class="material-symbols-outlined text-4xl text-primary">memory</span>
          </div>
          <span class="font-headline font-bold text-xl tracking-tight">Python</span>
        </div>
      </div>
    </div>
  </section>
</template>
