<template>
  <div>
    <!-- Navbar -->
    <NavigationBar />
    <!-- End of Navbar -->

    <!-- Hero Section -->
    <HeroSection />
    <!-- End of Hero Section -->
  </div>
</template>

<script>
import HeroSection from '~/components/HomePage/HeroSection.vue';
export default {
    name: "HomePage",
    components: { HeroSection }
}
</script>
