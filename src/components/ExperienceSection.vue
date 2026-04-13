<script setup>
import { useI18n } from 'vue-i18n'

const { t } = useI18n()
</script>

<template>
  <section id="experience" class="py-32 px-8 bg-surface-container-low">
    <div class="max-w-screen-xl mx-auto">
      <div class="flex flex-col md:flex-row justify-between items-end gap-8 mb-24">
        <div class="max-w-2xl">
          <h2 class="font-headline text-4xl md:text-6xl font-bold tracking-tighter text-on-background mb-6">{{ t('experience.title', { highlight: '' }) }}<span class="text-primary">{{ t('experience.highlight') }}</span> {{ t('experience.title', { highlight: '' }).split('{highlight}')[1] }}</h2>
          <p class="text-on-surface-variant text-lg leading-relaxed">{{ t('experience.description') }}</p>
        </div>
        <div class="text-right hidden md:block">
          <p class="text-primary font-bold font-headline text-5xl">{{ t('experience.year') }}</p>
          <p class="text-on-surface-variant tracking-widest uppercase text-xs">{{ t('experience.yearLabel') }}</p>
        </div>
      </div>

      <div class="space-y-12">
        <div class="group relative bg-surface-container p-12 rounded-xl transition-all duration-500 hover:bg-surface-container-high border-l-4 border-primary cursor-pointer">
          <div class="flex flex-col md:flex-row justify-between md:items-center gap-6">
            <div>
              <h4 class="text-2xl font-bold font-headline mb-2">{{ t('experience.job1Title') }}</h4>
              <p class="text-primary font-medium">{{ t('experience.job1Company') }}</p>
            </div>
            <div class="px-4 py-2 bg-surface-container-highest rounded text-sm font-mono text-on-surface-variant">
              {{ t('experience.job1Date') }}
            </div>
          </div>
          <p class="mt-8 text-on-surface-variant leading-relaxed max-w-4xl">
            {{ t('experience.job1Description') }}
          </p>
        </div>

        <div class="group relative bg-surface-container p-12 rounded-xl transition-all duration-500 hover:bg-surface-container-high border-l-4 border-secondary cursor-pointer">
          <div class="flex flex-col md:flex-row justify-between md:items-center gap-6">
            <div>
              <h4 class="text-2xl font-bold font-headline mb-2">{{ t('experience.job2Title') }}</h4>
              <p class="text-secondary font-medium">{{ t('experience.job2Company') }}</p>
            </div>
            <div class="px-4 py-2 bg-surface-container-highest rounded text-sm font-mono text-on-surface-variant">
              {{ t('experience.job2Date') }}
            </div>
          </div>
          <p class="mt-8 text-on-surface-variant leading-relaxed max-w-4xl">
            {{ t('experience.job2Description') }}
          </p>
        </div>
      </div>
    </div>
  </section>
</template>
