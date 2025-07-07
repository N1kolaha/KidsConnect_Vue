<template>
    <div class="card">
      <img src="/imgtemp.svg" alt="картинка" class="card-image" />
      
      <div class="card-content">
        <div class="upp">
        <div>
            <span class="head" v-for="(t,index) in data.title" :key="index">
               {{ t }}
            </span>
        </div>
        <div class="buttonsUp">
                <span v-if="data.firstL" class="free">Первое бесплатно</span>
               <span class ="price">{{ data.price }}</span>  
        </div>
        </div>


        <span class="hash">{{ data.hashtag }}</span>
        <span class="age"> 
            <img src="/user.svg" alt="возр"  />
            {{ data.age + " Лет"}}
        </span>
        <span class="street">
            <img src="/street.svg" alt="возр"  />
            {{ data.street }}
        </span>
        <span class="place">
            <img src="/map.svg" alt="возр"  />
            {{ data.place }}
        </span>
        <span class="down">
            <span>
            <span class="date" v-for="(t, index) in data.date" :key="index">
            {{ t  }}<span v-if="index < data.date.length - 1">, </span>
          </span>
          
          <span class="time" v-for="(t, index) in data.time" :key="index">
            {{ t  }}
          </span>
            </span>
            <NuxtLink :to="{ path: '/about', query: { title: JSON.stringify(data.title) } }">
                    <button class="more" >Подробнее</button>
          </NuxtLink>
        </span>
      </div>
      
    </div>
  </template>
  
  
  <script setup>
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
  
  .card-image {
    width: 175px;
    height: 175px;
    object-fit: cover;
    border-radius: 8px;
    flex-shrink: 0;
  }
  
  .card-content {
    flex: 1;
    display: flex;
    flex-direction: column;
    gap:10px;
  }


  .head{
    display:flex;
    font-weight: 700;

  }

  .hash{
    font-size: 14px;
    color:lightcoral;

  }

  .age{
    display:flex;
    gap:10px;
  }

  .street{
    display:flex;
    gap:10px;
  }

  .place{
    display:flex;
    gap:10px;
  }


  .date{
    font-weight: 700;

  }

  .time{
    background: #f7DAAB;
    margin:10px;
    font-weight: regular;
    padding:4px 15px;
    border-radius: 5px;
  }



  .upp{
    display:flex;
    justify-content: space-between;
    align-items: flex-start;
  }

  .down{
    display:flex;
    justify-content: space-between;
    align-items: center;
  }

  .buttonsUp{
    display: flex;
    gap:20px;
    text-align:right;
    align-items: center;
  }

  .free{
    font-weight: 700;
    padding:5px 15px;
    border-radius: 5px;
    border:#D86B79 2px solid;
  }

  .price{
    color:white;
    background-color: #D86B79;
    padding:5px 15px;
    border-radius: 5px;
    white-space: pre;

  }

  .more{
    border: none;
    color:white;
    border-radius: 5px;
    padding:10px 20px;
    font-family: 'Montserrat', sans-serif;

    background-color: #70232F;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }
  .more:hover {
  background-color: #A33645; 
}
  </style>
  