<template>
    <div class="cards-wrapper">
    <div class="card">
    <div class="card-content">


        <fieldset class="legend-container">
      <legend @click="toggle2" class="legend-header">
        <div class="legend-content-wrapper">
          <span class="legend-title">СОДЕРЖАНИЕ ПРОГРАММЫ
        </span>
         <img src="/arrow.svg" alt="картинка" class="arrow"   :class="{ open: isOpen2 }" />
        </div>
      </legend>
      <div v-if="isOpen2" class=".legend-bodyMain">
           
        <fieldset class="legend-container">
      <legend @click="toggle" class="legend-header">
        <div class="legend-content-wrapper">
          <span class="legend-title">Базовый уровень
        </span>
         <img src="/arrow.svg" alt="картинка" class="arrow"   :class="{ open: isOpen }" />
        </div>
      </legend>
      <div v-if="isOpen" class="legend-body">
            <Summary/>
      </div>
    </fieldset>


    <fieldset class="legend-container">
      <legend @click="toggle1" class="legend-header">
        <div class="legend-content-wrapper">
          <span class="legend-title">Углубленный уровень
        </span>
         <img src="/arrow.svg" alt="картинка" class="arrow"   :class="{ open: isOpen1 }" />
        </div>
      </legend>
      <div v-if="isOpen1" class="legend-body">
        <Summary/>
      </div>
    </fieldset>

       
      </div>
    </fieldset>

    </div>
    </div>
    </div>
</template>


<script setup>
  import Summary from './summary.vue'

 const isOpen = ref(false)
 const isOpen1 = ref(false)
 const isOpen2 = ref(false)


  
  function toggle() {
    isOpen.value = !isOpen.value
  }

  function toggle1() {
    isOpen1.value = !isOpen1.value
  }

  function toggle2() {
    isOpen2.value = !isOpen2.value
  }

defineProps({
data: Object
})
</script>
<style scoped>
.card {
display: flex;
gap: 16px;
background: #fff;
border-radius: 5px;
padding: 20px 20px;
box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
align-items: center;
font-size: 16px;
border-top: #70232F 3px solid;

}

.cards-wrapper {
width:100%;
margin: 0 auto;

}



.header{
font-weight: bold;
font-size: 18px;
color:#70232F;

}

.subbheader{
font-weight: bold;
font-size: 16px;
color:#70232F;

}

.card-content {
display: flex;
flex-direction: column;
gap:25px;
width:100%;
}

.legend-container {
    border: 0px; 
    padding: 0;
    border-radius: 5px;
    width:100%;
    margin:0px;
  }

  .legend-title{
    margin-bottom:10px;
    font-weight: bold;
font-size: 18px;
color:#70232F;
  }
    .legend-header {
    margin: 0;
    padding: 0;
    cursor: pointer;
    user-select: none;
    width: 100%; 
    font-weight: bold;
font-size: 16px;
color:#70232F;

  }
  
  .legend-content-wrapper {
    display: flex;
    align-items: center;
    width: 100%; 
  justify-content: space-between; /* Ключевое изменение */ 
  }
  
.legend-body{
    padding-left: 10px;
}
.legend-bodyMain{
    padding-left: 0px;
}

.legend-list {
  padding-left: 0;
  margin-top: 5px;
}

.legend-item {
    display: flex;
  justify-content: flex-start;
  gap: 10px;
  margin:5px;
  padding-left: 10px;
  }
  
  .number{
    color:#70232F;
  }
  .arrow {
    user-select: none;
     }
  
  .arrow.open {
    transform: rotate(180deg);
  }

  

</style>
