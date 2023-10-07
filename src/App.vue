<script setup>
import { RouterView } from 'vue-router';
import Navbar from '@/components/navbar/Navbar.vue';
</script>

<template>
  <div class="container mx-auto px-3 md:px-2">
    <Navbar/>
    <RouterView/>
  </div>
</template>

<style src="./assets/css/styles.css" />