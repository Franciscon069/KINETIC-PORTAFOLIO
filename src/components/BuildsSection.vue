<script setup>
import { useI18n } from 'vue-i18n'

const { t } = useI18n()
</script>

<template>
  <section id="builds" class="py-32 px-8 bg-surface">
    <div class="max-w-screen-xl mx-auto">
      <div class="mb-16">
        <p class="text-primary font-bold tracking-[0.3em] uppercase text-xs mb-4">{{ t('builds.badge') }}</p>
        <h2 class="font-headline text-4xl md:text-6xl font-bold tracking-tighter text-on-background">{{ t('builds.title') }}</h2>
      </div>

      <div class="grid md:grid-cols-2 gap-0 bg-surface-container rounded-2xl overflow-hidden shadow-2xl relative border border-outline-variant/10">
        <div class="relative h-96 md:h-full">
          <img 
            class="w-full h-full object-cover" 
            alt="Bio-Logix dashboard showing genetic algorithm data visualizations"
            src="https://lh3.googleusercontent.com/aida-public/AB6AXuCHBiBfCXI0hSTvnZ-rO1lBy0yFDTjxNaHgffyWpV_aGdINH8NisgIbO9XQE0ZB919mjejd6PiLl_4mP_xYCKsyREwiPgpblfE_xYSJ_tvlWt-aGhxYuIEelDsHhcedaMWOLbx_NS8ngxyOjbAFn5rwxzYl9rn-Svzx1_HdR5mbLQVeQWApF3WxP0DdOVF5BT1hR5bLF65pgixrfsQyMc7AcSJqEZ2B8v__aG2-GB5yw3qNRhjQb3-a-pNDRVISNx9UkZnlhdRSt0I"
          />
          <div class="absolute inset-0 bg-gradient-to-r from-surface-container via-transparent to-transparent hidden md:block"></div>
        </div>

        <div class="p-12 flex flex-col justify-center">
          <h3 class="font-headline text-5xl font-bold mb-6 tracking-tighter">{{ t('builds.projectTitle') }}</h3>
          <p class="text-on-surface-variant text-lg leading-relaxed mb-8">
            {{ t('builds.projectDescription') }}
          </p>

          <div class="grid grid-cols-2 gap-8 mb-12">
            <div>
              <p class="text-[10px] text-on-surface-variant tracking-[0.2em] uppercase mb-1">{{ t('builds.performance') }}</p>
              <p class="text-2xl font-bold font-headline text-primary">0.02ms <span class="text-sm font-normal text-on-surface-variant">{{ t('builds.perGen') }}</span></p>
            </div>
            <div>
              <p class="text-[10px] text-on-surface-variant tracking-[0.2em] uppercase mb-1">{{ t('builds.population') }}</p>
              <p class="text-2xl font-bold font-headline text-secondary">10k+ <span class="text-sm font-normal text-on-surface-variant">{{ t('builds.entities') }}</span></p>
            </div>
          </div>

          <div class="flex flex-wrap gap-4 mb-12">
            <span class="px-3 py-1 bg-surface-container-highest rounded text-xs font-medium text-on-surface flex items-center gap-2">
              <span class="w-1 h-1 rounded-full bg-primary"></span> React Three Fiber
            </span>
            <span class="px-3 py-1 bg-surface-container-highest rounded text-xs font-medium text-on-surface flex items-center gap-2">
              <span class="w-1 h-1 rounded-full bg-primary"></span> Web Workers
            </span>
          </div>

          <button class="w-fit glass-card px-10 py-4 text-on-background font-bold rounded-lg border border-primary/20 hover:bg-primary/10 transition-all flex items-center gap-3">
            {{ t('builds.viewDemo') }}
            <span class="material-symbols-outlined text-primary">rocket_launch</span>
          </button>
        </div>
      </div>
    </div>
  </section>
</template>
