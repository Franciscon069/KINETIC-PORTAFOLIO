<script setup>
import { ref, computed } from 'vue'
import { useI18n } from 'vue-i18n'

const { t, locale } = useI18n()

const navLinks = computed(() => [
  { label: t('nav.hero'), href: '#hero' },
  { label: t('nav.ecosystem'), href: '#ecosystem' },
  { label: t('nav.builds'), href: '#builds' },
  { label: t('nav.experience'), href: '#experience' },
  { label: t('nav.contact'), href: '#contact' },
])

const activeSection = ref('hero')
const isMenuOpen = ref(false)

const handleNavClick = (href) => {
  activeSection.value = href.replace('#', '')
  isMenuOpen.value = false
}

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const setLanguage = (lang) => {
  locale.value = lang
  localStorage.setItem('locale', lang)
}
</script>

<template>
  <nav class="fixed top-0 w-full z-50 bg-surface/40 backdrop-blur-xl glow-cyan">
    <div class="flex justify-between items-center px-8 py-4 max-w-screen-xl mx-auto">
      <div class="text-2xl font-bold tracking-tighter text-primary font-headline">{{ t('nav.title') }}</div>

      <div class="hidden md:flex gap-8 items-center">
        <a
          v-for="link in navLinks"
          :key="link.href"
          :href="link.href"
          :class="[
            'font-headline tracking-tighter transition-colors',
            activeSection === link.href.replace('#', '')
              ? 'text-primary font-bold border-b-2 border-primary pb-1'
              : 'text-on-surface-variant font-medium hover:text-primary/80'
          ]"
          @click="handleNavClick(link.href)"
        >
          {{ link.label }}
        </a>
      </div>

      <div class="hidden md:flex gap-2 items-center">
        <button 
          @click="setLanguage('en')"
          :class="['px-2 py-1 text-sm font-bold transition-all border-b-2 flex items-baseline gap-1', locale === 'en' ? 'text-primary border-primary' : 'text-on-surface-variant border-transparent hover:text-primary/80']"
        >
          EN <span class="text-[0.65rem] font-medium opacity-70">US</span>
        </button>
        <span class="text-on-surface-variant/50 text-sm">|</span>
        <button 
          @click="setLanguage('es')"
          :class="['px-2 py-1 text-sm font-bold transition-all border-b-2 flex items-baseline gap-1', locale === 'es' ? 'text-primary border-primary' : 'text-on-surface-variant border-transparent hover:text-primary/80']"
        >
          ES <span class="text-[0.65rem] font-medium opacity-70">Mx</span>
        </button>
      </div>

      <button 
        class="md:hidden flex flex-col gap-1.5 p-2 cursor-pointer"
        @click="toggleMenu"
        aria-label="Toggle menu"
      >
        <span 
          :class="[
            'w-6 h-0.5 bg-primary transition-all duration-300',
            isMenuOpen && 'rotate-45'
          ]"
          :style="isMenuOpen ? 'transform: translateY(8px)' : ''"
        ></span>
        <span 
          :class="[
            'w-6 h-0.5 bg-primary transition-all duration-300',
            isMenuOpen && 'opacity-0'
          ]"
        ></span>
        <span 
          :class="[
            'w-6 h-0.5 bg-primary transition-all duration-300',
            isMenuOpen && 'rotate-[-45deg]'
          ]"
          :style="isMenuOpen ? 'transform: translateY(-8px)' : ''"
        ></span>
      </button>
    </div>

    <div 
      :class="[
        'md:hidden overflow-hidden transition-all duration-300 ease-in-out',
        isMenuOpen ? 'max-h-96 opacity-100' : 'max-h-0 opacity-0'
      ]"
    >
      <div class="px-8 py-4 bg-surface-container border-t border-outline-variant/10">
        <div class="flex flex-col gap-4">
          <a
            v-for="link in navLinks"
            :key="link.href"
            :href="link.href"
            :class="[
              'font-headline tracking-tighter transition-colors py-2',
              activeSection === link.href.replace('#', '')
                ? 'text-primary font-bold'
                : 'text-on-surface-variant font-medium hover:text-primary/80'
            ]"
            @click="handleNavClick(link.href)"
          >
            {{ link.label }}
          </a>
        </div>
        <div class="flex gap-2 items-center mt-4 pt-4 border-t border-outline-variant/10">
          <button 
            @click="setLanguage('en')"
            :class="['px-2 py-1 text-sm font-bold transition-all border-b-2 flex items-baseline gap-1', locale === 'en' ? 'text-primary border-primary' : 'text-on-surface-variant border-transparent hover:text-primary/80']"
          >
            EN <span class="text-[0.65rem] font-medium opacity-70">US</span>
          </button>
          <span class="text-on-surface-variant/50 text-sm">|</span>
          <button 
            @click="setLanguage('es')"
            :class="['px-2 py-1 text-sm font-bold transition-all border-b-2 flex items-baseline gap-1', locale === 'es' ? 'text-primary border-primary' : 'text-on-surface-variant border-transparent hover:text-primary/80']"
          >
            ES <span class="text-[0.65rem] font-medium opacity-70">Mx</span>
          </button>
        </div>
      </div>
    </div>
  </nav>
</template>
