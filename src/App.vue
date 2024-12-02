<template>
  <div id="app">
    <HeroSection />
    <ServicesSection />
    <ContactSection />
    <WhatsApp />
    <ContactUs />
  </div>
</template>

<script>
import HeroSection from "./components/HeroSection.vue";
import ServicesSection from "./components/ServicesSection.vue";
import ContactSection from "./components/ContactSection.vue";
import WhatsApp from "./components/WhatsApp.vue"
import ContactUs from "./components/ContactUs.vue"

export default {
  name: "App",
  components: {
    HeroSection,
    ServicesSection,
    ContactSection,
    WhatsApp,
    ContactUs,
  },
};
</script>

<style>
/* Global styling can go here if needed */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: Arial, sans-serif;
  color: #333;
  line-height: 1.6;
}
</style>

