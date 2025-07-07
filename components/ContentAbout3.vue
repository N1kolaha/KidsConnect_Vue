<template>
    <div class="cards-wrapper">
    <div class="card">
    <div class="card-content">
        <div class="header">ОПИСАНИЕ</div>
        <div class="descr">{{ data.descr }}</div>

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



.card-content {
display: flex;
flex-direction: column;
gap:10px;
}



</style>
