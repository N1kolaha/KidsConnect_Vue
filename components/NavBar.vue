<template>
    <nav class="navbar">
      <div class="navbarLeft">
     <div class="search-container">
        <img src="/search.svg" alt="Поиск" class="search-icon" />
      <input
        type="text"
        placeholder="Поиск"
        class="search-input"
        v-model="searchQuery"
        @keyup.enter="onSearch"
      />
    </div>
    <div class="buttons">
      <button class="btn active-btn">Все</button>
      <button class="btn">Платные</button>
      <button class="btn">Бесплатные</button>
    </div>
    
        
    
</div>
<div class="map">
        
        <button class="btn">На карте</button>
        <img src="/map.svg" alt="карта" class="search-icon" />
    </div>
</nav>
</template>

<script setup>
import { ref } from 'vue'

const searchQuery = ref('')

function onSearch() {
  
}
</script>

<style>

.navbar{
    display:flex;
    justify-content: space-between;
}


.navbarLeft {
  display: flex;
  align-items: center;
  font-family: 'Montserrat', sans-serif;

}

.search-container {
  display: flex;
  align-items: center;
  background: white;
  border-radius: 5px;
  padding: 4px 12px;
  flex: 1;
  max-width: 240px;
  margin: 0 20px;
  font-family: 'Montserrat', sans-serif;

}

.search-input {
  border: none;
  outline: none;
  padding: 6px 8px;
  font-size: 14px;
  font-weight: regular;
}

.search-input::placeholder {
  font-family: 'Montserrat', sans-serif;
  font-weight: normal; 
  color: #D86B79; 
}



.search-icon {
  width: 18px;
  height: 18px;
}

.buttons {
  display: flex;
  gap: 20px;
}

.btn {
  background: transparent;
  border: none;
  color: #333333;
  font-weight: 600;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.2s ease;
  font-family: 'Montserrat', sans-serif;
  font-weight: regular;


}

.btn:hover {
  background-color: rgba(255 255 255 / 0.2);
}

.active-btn {
    padding: 10px 20px;

  background-color: white;
}
.map{
    display: flex;
  align-items: center;
    background: transparent;
  border: none;
  color: #333333;
  padding: 10px 20px;

  background-color: white;
  font-weight: 600;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.2s ease;
  font-family: 'Montserrat', sans-serif;
  font-weight: regular;
}

.map:hover {
    background-color: rgba(255 255 255 / 0.2);

}
</style>