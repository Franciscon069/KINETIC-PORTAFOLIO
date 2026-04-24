<script setup>
import { onMounted } from 'vue'
import { useI18n } from 'vue-i18n'

const { t } = useI18n()

const jobs = [
  { id: 1, color: 'primary' },
  { id: 2, color: 'secondary' },
  { id: 3, color: 'tertiary' }
]

onMounted(() => {
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('active');
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('#experience .reveal').forEach(el => observer.observe(el));
});
</script>

<template>
  <section id="experience" class="py-20 md:py-32 px-6 md:px-8 bg-surface-container-low overflow-hidden">
    <div class="max-w-screen-xl mx-auto">
      <div class="flex flex-col md:flex-row justify-between items-start md:items-end gap-8 mb-16 md:mb-24 reveal">
        <div class="max-w-2xl">
          <h2 class="font-headline text-4xl md:text-6xl font-bold tracking-tighter text-on-background mb-6">{{ t('experience.title') }}</h2>
          <p class="text-on-surface-variant text-base md:text-lg leading-relaxed">{{ t('experience.description') }}</p>
        </div>
        <div class="text-left md:text-right">
          <p class="text-primary font-bold font-headline text-5xl md:text-6xl">{{ t('experience.year') }}</p>
          <p class="text-on-surface-variant tracking-widest uppercase text-[10px] md:text-xs">{{ t('experience.yearLabel') }}</p>
        </div>
      </div>

      <div class="space-y-6 md:space-y-12">
        <div 
          v-for="job in jobs" 
          :key="job.id"
          :class="[
            'group relative bg-surface-container p-8 md:p-12 rounded-2xl transition-all duration-500 hover:bg-surface-container-high border-l-4 cursor-pointer reveal shadow-sm hover:shadow-xl',
            job.color === 'primary' ? 'border-primary' : job.color === 'secondary' ? 'border-secondary' : 'border-tertiary'
          ]"
        >
          <div class="flex flex-col md:flex-row justify-between md:items-center gap-4 md:gap-6">
            <div>
              <h4 class="text-xl md:text-2xl font-bold font-headline mb-2">{{ t(`experience.job${job.id}Title`) }}</h4>
              <p 
                :class="[
                  'font-medium text-sm md:text-base',
                  job.color === 'primary' ? 'text-primary' : job.color === 'secondary' ? 'text-secondary' : 'text-tertiary'
                ]"
              >
                {{ t(`experience.job${job.id}Company`) }}
              </p>
            </div>
            <div class="w-fit px-4 py-2 bg-surface-container-highest rounded text-xs font-mono text-on-surface-variant">
              {{ t(`experience.job${job.id}Date`) }}
            </div>
          </div>
          <p class="mt-6 md:mt-8 text-on-surface-variant text-sm md:text-base leading-relaxed max-w-4xl opacity-80 group-hover:opacity-100 transition-opacity">
            {{ t(`experience.job${job.id}Description`) }}
          </p>
        </div>
      </div>
    </div>
  </section>
</template>
