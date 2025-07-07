
<script setup>
  defineProps({
    data: String
  })
  </script>

<template>
    <nav class="navbar">
        <NuxtLink to="/" class="logo">
      <img :src="data" alt="Logo" class="logo-img" />
      <span class="logo-text">KidsConnect</span>
    </NuxtLink>
  
     
    </nav>
  </template>
  
  <style scoped>
  .navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 12px 40px;
    background-color: #70232F;
    font-family: 'Montserrat', sans-serif;
    border-radius: 15px;

  }
  
  .logo {
    display: flex;
    font-size: 32px;
    justify-content: space-between;

    font-weight: semibold;
    color: #ffffff;
    text-decoration: none;
    align-items: center; 
  }
  
  
  
  </style>
  