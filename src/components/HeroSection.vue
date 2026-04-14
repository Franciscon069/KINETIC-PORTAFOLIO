<script setup>
import { useI18n } from 'vue-i18n'

const { t, locale } = useI18n()
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
          {{ t('hero.title') }}<template v-if="locale === 'es'">,<br /></template><template v-else>, </template><span class="text-transparent bg-clip-text bg-gradient-to-br from-primary to-secondary">{{ t('hero.name') }}</span>
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
        <div class="relative w-full aspect-[3/4] bg-surface-container rounded-xl overflow-hidden shadow-2xl">
          <img 
            class="w-full h-full object-cover object-[center_20%]" 
            alt="Foto perfil Francisco Javier Hermosillo Aguila"
            src="../assets/images/FotoPersonal.jpeg"
          />
        </div>
      </div>
    </div>
  </section>
</template>
