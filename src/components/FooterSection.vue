<script setup>
import { useI18n } from 'vue-i18n'

const { t } = useI18n()
</script>

<template>
  <footer class="w-full py-12 border-t border-cyan-900/10 bg-surface-dim">
    <div class="flex flex-col md:flex-row justify-between items-center px-8 max-w-screen-xl mx-auto gap-8">
      <div class="text-primary font-black text-xl tracking-tighter">{{ t('nav.title') }}</div>

      <div class="flex gap-8">
        <a class="font-label text-xs uppercase tracking-widest text-on-surface-variant hover:text-primary transition-colors opacity-80 hover:opacity-100" href="https://github.com/Franciscon069">{{ t('footer.github') }}</a>
        <a class="font-label text-xs uppercase tracking-widest text-on-surface-variant hover:text-primary transition-colors opacity-80 hover:opacity-100" href="https://www.linkedin.com/public-profile/settings/?trk=d_flagship3_profile_self_view_public_profile&lipi=urn%3Ali%3Apage%3Ad_flagship3_profile_view_base%3BHyFmu9XXTN6kLeQaZVSgmA%3D%3D">{{ t('footer.linkedin') }}</a>
        <a class="font-label text-xs uppercase tracking-widest text-on-surface-variant hover:text-primary transition-colors opacity-80 hover:opacity-100" href="#">{{ t('footer.computrabajo') }}</a>
      </div>

      <p class="font-label text-xs uppercase tracking-widest text-on-surface-variant">
        {{ t('footer.copyright') }}
      </p>
    </div>
  </footer>
</template>
