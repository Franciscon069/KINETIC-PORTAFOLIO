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
      </div>

      <div class="grid grid-cols-2 md:grid-cols-6 gap-px bg-outline-variant/10 rounded-xl overflow-hidden">
        <div class="bg-surface group p-8 flex flex-col items-center justify-center gap-6 hover:bg-surface-container transition-all duration-500">
          <div class="w-16 h-16 rounded-full bg-surface-container-high flex items-center justify-center group-hover:scale-110 transition-transform">
            <span class="material-symbols-outlined text-4xl text-primary">terminal</span>
          </div>
          <span class="font-headline font-bold tracking-tight text-center">Python</span>
        </div>

        <div class="bg-surface group p-8 flex flex-col items-center justify-center gap-6 hover:bg-surface-container transition-all duration-500">
          <div class="w-16 h-16 rounded-full bg-surface-container-high flex items-center justify-center group-hover:scale-110 transition-transform">
            <span class="material-symbols-outlined text-4xl text-secondary">local_cafe</span>
          </div>
          <span class="font-headline font-bold tracking-tight text-center">Java</span>
        </div>

        <div class="bg-surface group p-8 flex flex-col items-center justify-center gap-6 hover:bg-surface-container transition-all duration-500">
          <div class="w-16 h-16 rounded-full bg-surface-container-high flex items-center justify-center group-hover:scale-110 transition-transform">
            <span class="material-symbols-outlined text-4xl text-primary">code</span>
          </div>
          <span class="font-headline font-bold tracking-tight text-center">JavaScript</span>
        </div>

        <div class="bg-surface group p-8 flex flex-col items-center justify-center gap-6 hover:bg-surface-container transition-all duration-500">
          <div class="w-16 h-16 rounded-full bg-surface-container-high flex items-center justify-center group-hover:scale-110 transition-transform">
            <span class="material-symbols-outlined text-4xl text-secondary">fact_check</span>
          </div>
          <span class="font-headline font-bold tracking-tight text-center">TypeScript</span>
        </div>

        <div class="bg-surface group p-8 flex flex-col items-center justify-center gap-6 hover:bg-surface-container transition-all duration-500">
          <div class="w-16 h-16 rounded-full bg-surface-container-high flex items-center justify-center group-hover:scale-110 transition-transform">
            <span class="material-symbols-outlined text-4xl text-primary">api</span>
          </div>
          <span class="font-headline font-bold tracking-tight text-center">Laravel</span>
        </div>

        <div class="bg-surface group p-8 flex flex-col items-center justify-center gap-6 hover:bg-surface-container transition-all duration-500">
          <div class="w-16 h-16 rounded-full bg-surface-container-high flex items-center justify-center group-hover:scale-110 transition-transform">
            <span class="material-symbols-outlined text-4xl text-secondary">database</span>
          </div>
          <span class="font-headline font-bold tracking-tight text-center">SQL</span>
        </div>

        <div class="bg-surface group p-8 flex flex-col items-center justify-center gap-6 hover:bg-surface-container transition-all duration-500">
          <div class="w-16 h-16 rounded-full bg-surface-container-high flex items-center justify-center group-hover:scale-110 transition-transform">
            <span class="material-symbols-outlined text-4xl text-primary">layers</span>
          </div>
          <span class="font-headline font-bold tracking-tight text-center">Vue.js</span>
        </div>

        <div class="bg-surface group p-8 flex flex-col items-center justify-center gap-6 hover:bg-surface-container transition-all duration-500">
          <div class="w-16 h-16 rounded-full bg-surface-container-high flex items-center justify-center group-hover:scale-110 transition-transform">
            <span class="material-symbols-outlined text-4xl text-secondary">animation</span>
          </div>
          <span class="font-headline font-bold tracking-tight text-center">React</span>
        </div>

        <div class="bg-surface group p-8 flex flex-col items-center justify-center gap-6 hover:bg-surface-container transition-all duration-500">
          <div class="w-16 h-16 rounded-full bg-surface-container-high flex items-center justify-center group-hover:scale-110 transition-transform">
            <span class="material-symbols-outlined text-4xl text-primary">html</span>
          </div>
          <span class="font-headline font-bold tracking-tight text-center">HTML 5</span>
        </div>

        <div class="bg-surface group p-8 flex flex-col items-center justify-center gap-6 hover:bg-surface-container transition-all duration-500">
          <div class="w-16 h-16 rounded-full bg-surface-container-high flex items-center justify-center group-hover:scale-110 transition-transform">
            <span class="material-symbols-outlined text-4xl text-secondary">palette</span>
          </div>
          <span class="font-headline font-bold tracking-tight text-center">Tailwindcss</span>
        </div>

        <div class="bg-surface group p-8 flex flex-col items-center justify-center gap-6 hover:bg-surface-container transition-all duration-500">
          <div class="w-16 h-16 rounded-full bg-surface-container-high flex items-center justify-center group-hover:scale-110 transition-transform">
            <span class="material-symbols-outlined text-4xl text-primary">commit</span>
          </div>
          <span class="font-headline font-bold tracking-tight text-center">Git</span>
        </div>

        <div class="bg-surface group p-8 flex flex-col items-center justify-center gap-6 hover:bg-surface-container transition-all duration-500">
          <div class="w-16 h-16 rounded-full bg-surface-container-high flex items-center justify-center group-hover:scale-110 transition-transform">
            <span class="material-symbols-outlined text-4xl text-secondary">hub</span>
          </div>
          <span class="font-headline font-bold tracking-tight text-center">GitHub</span>
        </div>
      </div>
    </div>
  </section>
</template>
