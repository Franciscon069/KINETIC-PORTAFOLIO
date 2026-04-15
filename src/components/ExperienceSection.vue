<script setup>
import { useI18n } from 'vue-i18n'

const { t } = useI18n()

const jobs = [
  { id: 1, color: 'primary' },
  { id: 2, color: 'secondary' },
  { id: 3, color: 'tertiary' }
]
</script>

<template>
  <section id="experience" class="py-32 px-8 bg-surface-container-low">
    <div class="max-w-screen-xl mx-auto">
      <div class="flex flex-col md:flex-row justify-between items-end gap-8 mb-24">
        <div class="max-w-2xl">
          <h2 class="font-headline text-4xl md:text-6xl font-bold tracking-tighter text-on-background mb-6">{{ t('experience.title') }}</h2>
          <p class="text-on-surface-variant text-lg leading-relaxed">{{ t('experience.description') }}</p>
        </div>
        <div class="text-right hidden md:block">
          <p class="text-primary font-bold font-headline text-5xl">{{ t('experience.year') }}</p>
          <p class="text-on-surface-variant tracking-widest uppercase text-xs">{{ t('experience.yearLabel') }}</p>
        </div>
      </div>

      <div class="space-y-12">
        <div 
          v-for="job in jobs" 
          :key="job.id"
          :class="[
            'group relative bg-surface-container p-12 rounded-xl transition-all duration-500 hover:bg-surface-container-high border-l-4 cursor-pointer',
            job.color === 'primary' ? 'border-primary' : job.color === 'secondary' ? 'border-secondary' : 'border-tertiary'
          ]"
        >
          <div class="flex flex-col md:flex-row justify-between md:items-center gap-6">
            <div>
              <h4 class="text-2xl font-bold font-headline mb-2">{{ t(`experience.job${job.id}Title`) }}</h4>
              <p 
                :class="[
                  'font-medium',
                  job.color === 'primary' ? 'text-primary' : job.color === 'secondary' ? 'text-secondary' : 'text-tertiary'
                ]"
              >
                {{ t(`experience.job${job.id}Company`) }}
              </p>
            </div>
            <div class="px-4 py-2 bg-surface-container-highest rounded text-sm font-mono text-on-surface-variant">
              {{ t(`experience.job${job.id}Date`) }}
            </div>
          </div>
          <p class="mt-8 text-on-surface-variant leading-relaxed max-w-4xl">
            {{ t(`experience.job${job.id}Description`) }}
          </p>
        </div>
      </div>
    </div>
  </section>
</template>
