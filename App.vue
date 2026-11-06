<template>
  <div id="app" class="site-shell">
    <Header />
    <router-view />
    <Footer />
    <button class="back-to-top" type="button" @click="scrollTop" aria-label="Back to top">
      ↑
    </button>
  </div>
</template>

<script setup>
import { onMounted } from 'vue'
import { useRouter } from 'vue-router'
import Header from '@/components/Header.vue'
import Footer from '@/components/Footer.vue'

const router = useRouter()
const scrollTop = () => window.scrollTo({ top: 0, behavior: 'smooth' })

onMounted(() => {
  router.beforeEach(() => {
    window.scrollTo({ top: 0, behavior: 'smooth' })
  })
})
</script>
