<script setup>
import { useI18n } from 'vue-i18n'

const { t } = useI18n()
</script>

<template>
  <section id="hero" class="relative min-h-screen flex items-center pt-20 px-8 overflow-hidden bg-surface">
    <div class="absolute inset-0 z-0 opacity-20 pointer-events-none">
      <div class="absolute top-1/4 -left-20 w-96 h-96 bg-primary rounded-full blur-[128px]"></div>
      <div class="absolute bottom-1/4 -right-20 w-96 h-96 bg-secondary rounded-full blur-[128px]"></div>
    </div>

    <div class="max-w-screen-xl mx-auto w-full grid md:grid-cols-12 gap-12 items-center relative z-10">
      <div class="md:col-span-8">
        <div class="mb-6 inline-flex items-center gap-2 px-3 py-1 rounded-full bg-surface-container-highest/50 backdrop-blur-md">
          <span class="w-2 h-2 rounded-full bg-primary animate-pulse"></span>
          <span class="text-[10px] uppercase tracking-[0.2em] font-bold text-primary-fixed">{{ t('hero.badge') }}</span>
        </div>

        <h1 class="font-headline text-5xl md:text-8xl font-bold tracking-tighter leading-[0.9] text-on-background mb-8">
          {{ t('hero.title', { highlight: '' }) }}<span class="text-transparent bg-clip-text bg-gradient-to-br from-primary to-secondary">{{ t('hero.highlight') }}</span> {{ t('hero.title', { highlight: '' }).split('{highlight}')[1] }}
        </h1>

        <p class="font-body text-lg md:text-xl text-on-surface-variant max-w-2xl mb-12 leading-relaxed">
          {{ t('hero.description', { school: t('hero.school') }) }}
        </p>

        <div class="flex flex-wrap gap-6">
          <a class="px-8 py-4 bg-gradient-to-br from-primary-container to-secondary-container text-on-primary-fixed font-bold rounded-lg hover:scale-95 transition-transform flex items-center gap-3" href="#builds">
            {{ t('hero.ctaExplore') }}
            <span class="material-symbols-outlined">arrow_forward</span>
          </a>
          <a class="px-8 py-4 bg-surface-bright/10 backdrop-blur-xl border border-outline-variant/20 text-on-background font-bold rounded-lg hover:bg-surface-bright/20 transition-all" href="#contact">
            {{ t('hero.ctaContact') }}
          </a>
        </div>
      </div>

      <div class="md:col-span-4 hidden md:block">
        <div class="relative w-full aspect-square bg-surface-container rounded-xl overflow-hidden shadow-2xl">
          <div class="absolute inset-0 bg-gradient-to-t from-background to-transparent opacity-60"></div>
          <img 
            class="w-full h-full object-cover grayscale brightness-75 contrast-125" 
            alt="Abstract 3D rendered geometric structures"
            src="https://lh3.googleusercontent.com/aida-public/AB6AXuAGn0XwIgrb23KOH_YIS7u76Y-ToXn8Raxt8-Ns57hOVIFQM2XYAo-Kc7MJRUjkqPSVNQeteLhzkIqAdhpKPXPYWJu2P7we1YnHGiLzMzx17Mb7ItJk2hoTw81_E4oBEWOoiIQ-e5JeQyig8EL6HwJFtU7oBUOhZZbRxPlKbDEsdZh8wkkRcVU8He2ya1YMCIvtew5LpAjSRdMoBNqB0z1CB_yjC7fgkFncb8Ezuy_51xRoljsPBmrPgfpYXYCD8kdBi5PU_lbgIG0"
          />
          <div class="absolute bottom-6 left-6 right-6">
            <div class="glass-card p-4 rounded-lg border border-outline-variant/10">
              <div class="flex justify-between items-end">
                <div>
                  <p class="text-[10px] text-primary tracking-widest uppercase mb-1">Current Node</p>
                  <p class="font-headline font-bold text-xl">UPA_SYSTEM_01</p>
                </div>
                <span class="material-symbols-outlined text-4xl text-primary/40">sensors</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
