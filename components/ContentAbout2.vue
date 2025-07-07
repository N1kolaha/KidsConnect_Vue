<template>
    <div class="cards-wrapper">
<div class="card">
  
  <div class="card-content">
    <div class="upp">
    <div class="header">ГРУППЫ</div>
    <div class="subheader">Этап начальной подготовки</div>

    <span class="age"> 
        <img src="/teach.svg" alt="возр"  />
        {{ data.teacher }}
    </span>
    <span class="street">
        <img src="/studen.svg" alt="возр"  />
        {{ data.seats }}
    </span>
    <span class="place">
        <img src="/course.svg" alt="возр"  />
        {{ data.course }}
    </span>
   
</div>

<div class="down">
    <div class="header">РАСПИСАНИЕ ЗАНЯТИЙ</div>

    <span class = "subdown">      <img src="/time.svg" alt="возр"  />

            <span class="date" v-for="(t, index) in data.date" :key="index">
            {{ t  }}<span v-if="index < data.date.length - 1">, </span>
          </span>
        </span>
        <span class = "subdown">     <img src="/time.svg" alt="возр"  />


          <span class="time" v-for="(t, index) in data.time" :key="index">
            {{ t  }}
          </span>
            </span>
</div>



  </div>
  
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

.cards-wrapper {
width:100%;
margin: 0 auto;

}



.header{
font-weight: bold;
font-size: 18px;
color:#70232F;

}

.subheader{
    font-size: 16px;
    color:#333333;
    font-weight: bold;


}


.card-image {
width: 200px;
height: 200px;
object-fit: cover;
border-radius: 8px;
flex-shrink: 0;
}

.card-content {
display: flex;
flex-direction: row;
gap:20px;
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
font-weight: regular;
padding:4px 15px;
border-radius: 5px;
}



.upp{
display:flex;
flex-direction: column;
align-items: flex-start;
gap:10px;
}

.down{
display:flex;
flex-direction: column;
align-items: flex-start;
gap:10px;

}
.subdown{
    display:flex;
    align-items: center;
    gap:10px;
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
font-size: 16px;
font-weight: bold;


}
.more:hover {
background-color: #A33645; 
}
</style>
