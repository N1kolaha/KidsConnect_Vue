<template>
    <div class="cards-wrapper">
      <div class="header">Силовой спорт</div>
      <BuildCard
        v-for="(card, index) in buildCardData1"
        :key="index"
        :data="card"
      />
      <div class="header">Единоборства</div>
      <BuildCard
        v-for="(card, index) in buildCardData2"
        :key="index"
        :data="card"
      />
      <div class="header">Единоборства</div>
      <BuildCard
        v-for="(card, index) in buildCardData2"
        :key="index"
        :data="card"
      />
      <div class="header">Единоборства</div>
      <BuildCard
        v-for="(card, index) in buildCardData2"
        :key="index"
        :data="card"
      />
    </div>
  </template>
  
  <script setup>
  import BuildCard from './BuildCard.vue'
  import { buildCardData1 } from './BuildCardData.js'
  import { buildCardData2 } from './BuildCardData.js'


  </script>
  
  <style scoped>
  .cards-wrapper {
    width:900px;
    margin: 0 auto;
    padding: 24px;
    display: flex;
    flex-direction: column;
    gap: 20px;
  }
  .header{
    font-weight: bold;
    font-size: 24px;

  }
  </style>
  