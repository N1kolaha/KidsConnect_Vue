<template>
    <div class="container">
      <TopNavBar data="/logo.svg"/>
      <main class="main">
        <NavBar />
        <div class="mainCont">
          <div class="mainLeft">
          <Content />
        </div>
        <div class="mainRight">
          <Filters />
        </div>
        </div>
        
       
        <slot />
      </main>
    </div>
  </template>
  
  <script setup>
  import TopNavBar from '~/components/TopNavBar.vue'
  import NavBar from '~/components/NavBar.vue'
  import Content from '~/components/Content.vue'
  import Filters from '~/components/Filters.vue'
  
  
  
  </script>
  <style >
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
  
  .mainCont{
    display:flex;
    flex-direction: row;
  }
  
  
  </style>