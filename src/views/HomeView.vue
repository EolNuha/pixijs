<script setup>
import Header from '../components/HeaderComp.vue'
import ImageSlider from '../components/ImageSlider.vue'
import VideoComp from '../components/VideoComp.vue'
import PixiJS from '../components/PixiJs.vue'
import ContactUs from '../components/ContactUs.vue'
import Footer from '../components/FooterComp.vue'
</script>

<template>
  <Header />
  <div class="main">
    <ImageSlider />
    <VideoComp />
    <PixiJS />
    <ContactUs />
  </div>
  <Footer />
</template>

<style lang="scss">
.main {
  max-width: 1280px;
  padding: 0 20px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  gap: 100px;
  padding: 40px 20px;
}
</style>
