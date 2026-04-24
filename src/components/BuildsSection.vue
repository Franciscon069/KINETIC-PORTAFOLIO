<script setup>
import { onMounted } from 'vue'
import { useI18n } from 'vue-i18n'

const { t } = useI18n()

onMounted(() => {
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('active');
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('#builds .reveal').forEach(el => observer.observe(el));
});
</script>

<template>
  <section id="builds" class="py-20 md:py-32 px-6 md:px-8 bg-surface overflow-hidden">
    <div class="max-w-screen-xl mx-auto">
      <div class="mb-12 md:mb-16 reveal">
        <p class="text-primary font-bold tracking-[0.3em] uppercase text-[10px] md:text-xs mb-4">{{ t('builds.badge') }}</p>
        <h2 class="font-headline text-4xl md:text-6xl font-bold tracking-tighter text-on-background">{{ t('builds.title') }}</h2>
      </div>

      <div class="grid md:grid-cols-2 gap-0 bg-surface-container rounded-3xl overflow-hidden shadow-2xl relative border border-outline-variant/10 reveal">
        <div class="relative h-64 sm:h-80 md:h-full group/img overflow-hidden">
          <img 
            class="w-full h-full object-cover transition-transform duration-700 group-hover/img:scale-110" 
            alt="Bio-Logix dashboard showing genetic algorithm data visualizations"
            src="https://lh3.googleusercontent.com/aida-public/AB6AXuCHBiBfCXI0hSTvnZ-rO1lBy0yFDTjxNaHgffyWpV_aGdINH8NisgIbO9XQE0ZB919mjejd6PiLl_4mP_xYCKsyREwiPgpblfE_xYSJ_tvlWt-aGhxYuIEelDsHhcedaMWOLbx_NS8ngxyOjbAFn5rwxzYl9rn-Svzx1_HdR5mbLQVeQWApF3WxP0DdOVF5BT1hR5bLF65pgixrfsQyMc7AcSJqEZ2B8v__aG2-GB5yw3qNRhjQb3-a-pNDRVISNx9UkZnlhdRSt0I"
          />
          <div class="absolute inset-0 bg-gradient-to-r from-surface-container via-transparent to-transparent hidden md:block"></div>
          <div class="absolute inset-0 bg-gradient-to-t from-surface-container via-transparent to-transparent md:hidden"></div>
        </div>

        <div class="p-8 md:p-12 lg:p-16 flex flex-col justify-center">
          <h3 class="font-headline text-3xl md:text-5xl font-bold mb-6 tracking-tighter">{{ t('builds.projectTitle') }}</h3>
          <p class="text-on-surface-variant text-base md:text-lg leading-relaxed mb-8">
            {{ t('builds.projectDescription') }}
          </p>

          <div class="grid grid-cols-2 gap-6 md:gap-8 mb-10 md:mb-12">
            <div>
              <p class="text-[10px] text-on-surface-variant tracking-[0.2em] uppercase mb-1">{{ t('builds.performance') }}</p>
              <p class="text-xl md:text-2xl font-bold font-headline text-primary">0.02ms <span class="text-xs md:text-sm font-normal text-on-surface-variant">{{ t('builds.perGen') }}</span></p>
            </div>
            <div>
              <p class="text-[10px] text-on-surface-variant tracking-[0.2em] uppercase mb-1">{{ t('builds.population') }}</p>
              <p class="text-xl md:text-2xl font-bold font-headline text-secondary">10k+ <span class="text-xs md:text-sm font-normal text-on-surface-variant">{{ t('builds.entities') }}</span></p>
            </div>
          </div>

          <div class="flex flex-wrap gap-3 md:gap-4 mb-10 md:mb-12">
            <span class="px-3 py-1 bg-surface-container-highest rounded-full text-[10px] md:text-xs font-medium text-on-surface flex items-center gap-2 border border-outline-variant/10">
              <span class="w-1.5 h-1.5 rounded-full bg-primary"></span> React Three Fiber
            </span>
            <span class="px-3 py-1 bg-surface-container-highest rounded-full text-[10px] md:text-xs font-medium text-on-surface flex items-center gap-2 border border-outline-variant/10">
              <span class="w-1.5 h-1.5 rounded-full bg-primary"></span> Web Workers
            </span>
          </div>

          <button class="w-full sm:w-fit glass-card px-8 md:px-10 py-4 text-on-background font-bold rounded-xl border border-primary/20 hover:bg-primary/10 transition-all flex items-center justify-center gap-3 active:scale-95 shadow-lg shadow-primary/5">
            {{ t('builds.viewDemo') }}
            <span class="material-symbols-outlined text-primary text-xl">rocket_launch</span>
          </button>
        </div>
      </div>
    </div>
  </section>
</template>
