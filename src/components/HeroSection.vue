<script setup>
import { useI18n } from 'vue-i18n'

const { t, locale } = useI18n()
</script>

<template>
  <section id="hero" class="relative min-h-screen flex items-center pt-28 pb-16 md:pt-20 px-6 md:px-8 overflow-hidden bg-surface">
    <div class="absolute inset-0 z-0 opacity-20 pointer-events-none">
      <div class="absolute top-1/4 -left-20 w-64 h-64 md:w-96 md:h-96 bg-primary rounded-full blur-[80px] md:blur-[128px]"></div>
      <div class="absolute bottom-1/4 -right-20 w-64 h-64 md:w-96 md:h-96 bg-secondary rounded-full blur-[80px] md:blur-[128px]"></div>
    </div>

    <div class="max-w-screen-xl mx-auto w-full relative z-10 flex flex-col md:grid md:grid-cols-12 gap-8 md:gap-12 items-center">
      <!-- Imagen de perfil para móviles (Centrada y circular) -->
      <div class="md:hidden flex justify-center w-full mb-4">
        <div class="relative group">
          <div class="absolute -inset-1 bg-gradient-to-r from-primary to-secondary rounded-full blur opacity-25 group-hover:opacity-50 transition duration-1000 group-hover:duration-200"></div>
          <div class="relative w-32 h-32 rounded-full overflow-hidden border-2 border-primary/20 shadow-2xl">
            <img 
              class="w-full h-full object-cover object-[center_20%]" 
              alt="Foto perfil Francisco Javier Hermosillo Aguila"
              src="../assets/images/FotoPersonal.jpeg"
            />
          </div>
        </div>
      </div>

      <div class="md:col-span-7 lg:col-span-8 flex flex-col items-center md:items-start text-center md:text-left">
        <div class="mb-4 md:mb-6 inline-flex items-center gap-2 px-3 py-1 rounded-full bg-surface-container-highest/50 backdrop-blur-md">
          <span class="w-2 h-2 rounded-full bg-primary animate-pulse"></span>
          <span class="text-[10px] uppercase tracking-[0.2em] font-bold text-primary-fixed">{{ t('hero.badge') }}</span>
        </div>

        <h1 class="font-headline text-4xl sm:text-5xl md:text-8xl font-bold tracking-tighter leading-[1.1] md:leading-[0.9] text-on-background mb-6 md:mb-8">
          {{ t('hero.title') }}<template v-if="locale === 'es'">,<br /></template><template v-else>, </template><span class="text-transparent bg-clip-text bg-gradient-to-br from-primary to-secondary">{{ t('hero.name') }}</span>
        </h1>

        <p class="font-body text-base md:text-xl text-on-surface-variant max-w-2xl mb-10 md:mb-12 leading-relaxed px-4 md:px-0">
          {{ t('hero.description', { school: t('hero.school') }) }}
        </p>

        <div class="flex flex-col sm:flex-row gap-4 md:gap-6 w-full sm:w-auto px-6 sm:px-0">
          <a class="px-8 py-4 bg-gradient-to-br from-primary-container to-secondary-container text-on-primary-fixed font-bold rounded-xl hover:scale-95 transition-transform flex items-center justify-center gap-3 shadow-xl shadow-primary/10" href="#builds">
            {{ t('hero.ctaExplore') }}
            <span class="material-symbols-outlined">arrow_forward</span>
          </a>
          <a class="px-8 py-4 bg-surface-bright/10 backdrop-blur-xl border border-outline-variant/20 text-on-background font-bold rounded-lg hover:bg-surface-bright/20 transition-all text-center" href="#contact">
            {{ t('hero.ctaContact') }}
          </a>
        </div>
      </div>

      <!-- Imagen de perfil para Escritorio (Oculta en móvil) -->
      <div class="hidden md:block md:col-span-5 lg:col-span-4">
        <div class="relative w-full aspect-[3/4] bg-surface-container rounded-xl overflow-hidden shadow-2xl border border-outline-variant/10">
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
