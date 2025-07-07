<template>
    <div class="container">
      <TopNavBar data="/logo2.svg"/>
      <main class="main">
        <NavBarAbout />
        <div class="mainContAbout">
          <ContentAbout v-if="foundData" :data="foundData"/>
          <ContentAbout2 v-if="foundData" :data="foundData"/>
          <ContentAbout3 v-if="foundData" :data="foundData"/>
          <ContentAbout4 v-if="foundData" :data="foundData"/>



        </div>
      </main>
    </div>
  </template>
  
  <script setup>
  import TopNavBar from '~/components/TopNavBar.vue'
  import NavBarAbout from '~/components/NavBarAbout.vue'
  import Content from '~/components/Content.vue'
  import Filters from '~/components/Filters.vue'
  import { useRoute } from 'vue-router'
import { ref, computed } from 'vue'
import { buildCardData1 } from '~/components/BuildCardData.js'  
import { buildCardData2 } from '~/components/BuildCardData.js'  

import BuildCard from '~/components/BuildCard.vue'

import ContentAbout from '~/components/ContentAbout.vue'
import ContentAbout2 from '~/components/ContentAbout2.vue'
import ContentAbout3 from '~/components/ContentAbout3.vue'
import ContentAbout4 from '~/components/ContentAbout4.vue'





const route = useRoute()

const title = route.query.title ? JSON.parse(route.query.title) : []

const foundData = computed(() => {
  return (
    buildCardData1.find(item => JSON.stringify(item.title) === JSON.stringify(title)) ||
    buildCardData2.find(item => JSON.stringify(item.title) === JSON.stringify(title)) ||
    null
  )
})
  
  
  </script>
  <style>
  body {
    font-family: 'Montserrat', sans-serif;
  }
  .container {
    max-width: 1400px;

    margin: 0 auto;    
    padding: 0 16px;           
  }
  .main {
    background-color: #EFEFEF;
    border-radius: 15px;
    padding: 40px 40px;           
    margin-top: 30px;
  
  }
  
  .mainContAbout{
    margin-top:20px;
    display:flex;
    flex-direction: column;
    gap:20px;
  }
  
  
  </style>