<template>
  <div>
    <Header />
    <keep-alive><Nuxt></Nuxt></keep-alive>
    <Footer />
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import Footer from "@/components/Footer.vue";
export default {
  components: {
    Header,
    Footer,
  },
};
</script>
