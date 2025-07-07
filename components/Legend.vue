<template>
    <fieldset class="legend-container">
      <legend @click="toggle" class="legend-header">
        <div class="legend-content-wrapper">
          <span class="legend-title">{{titleN}} <span v-if="sum > 0">&nbsp;&nbsp;<span class="number">{{ sum }}</span></span>
        </span>
         <img src="/arrow.svg" alt="картинка" class="arrow"   :class="{ open: isOpen }" />
        </div>
      </legend>
      <div v-if="isOpen" class="legend-body">
        
            <ul class="legend-list">
      <li v-for="tag in uniqueHashtags" :key="tag" class="legend-item">
       <span>•</span> <span>{{ tag.slice(1) }} </span >    <span class="number">{{ hashtagCounts[tag] }}</span>
      </li>
    </ul>
       
      </div>
    </fieldset>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  
  import { computed } from 'vue'

  const props = defineProps({
  data: {
    type: Array,
    required: true
  },
  titleN:{
    type: String,
    required:true
  }
})  
  const isOpen = ref(false)
  
  function toggle() {
    isOpen.value = !isOpen.value
  }


  const hashtagCounts = computed(() => {
  const counts = {}
  for (const item of props.data) {
    counts[item.hashtag] = (counts[item.hashtag] || 0) + 1
  }
  return counts
})

const uniqueHashtags = computed(() => Object.keys(hashtagCounts.value))

const sum = computed(() =>
  Object.values(hashtagCounts.value).reduce((acc, count) => acc + count, 0)
)

  </script>
  
  <style scoped>
  .legend-container {
    border: 0px;
    padding: 0;
    border-radius: 5px;
  }

    .legend-header {
    margin: 0;
    padding: 0;
    cursor: pointer;
    user-select: none;
    width: 100%; /* Добавлено */

  }
  
  .legend-content-wrapper {
    display: flex;
    align-items: center;
    width: 100%; 
  justify-content: space-between; /* Ключевое изменение */ 
  }
  
  .legend-item {
    display: flex;
  justify-content: flex-start;
  gap: 15px;
  margin:5px;
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

  .legend-list {
  padding-left: 0;
  margin-top: 5px;
}
  
  </style>
  