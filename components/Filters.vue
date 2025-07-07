<script setup>
import Legend from './Legend.vue'
import { buildCardData1 } from './BuildCardData';
import { buildCardData2 } from './BuildCardData';

</script>
<template>
    <div class="filters">
        <div class="header">Фильтры</div>
            <div class="mainF">
                <label for="age" class="age">Возраст:</label><br>
                 <select v-model="selectedAge" id="age">
                 <option value="">Любой</option>
                 <option v-for="age in ageOptions" :key="age" :value="age">
                  {{ age }}
                  </option>
                     </select>

                     <div class="gender">
                        <div class="genderH">Пол</div>
                            <div class="genders"> 
                                <label>
                    <input type="checkbox"  value="Мужской" />
                    Мужской
                    </label>

                    <label>
                    <input type="checkbox"  value="Женский" />
                    Женский
                    </label>
                </div>
                        
                     </div>

                     <div class="cata">Каталог</div>
                     <div class="legends">

                        <Legend :data="buildCardData1" titleN="Силовой спорт"/>
                        <Legend :data="buildCardData2" titleN="Единоборства"/>
                        <Legend :data="[]" titleN="ДПИ и ремесла"/>
                        <Legend :data="[]" titleN="Техническое конструирование"/>
                        <Legend :data="[]" titleN="Словесность"/>
                        <Legend :data="[]" titleN="Иностранные языки"/>
                        <Legend :data="[]" titleN="Развитие интеллекта"/>
                        <Legend :data="[]" titleN="Информационные технологии"/>
                        <Legend :data="[]" titleN="История и Традиции"/>
                        <Legend :data="[]" titleN="Педагогика"/>
                        <Legend :data="[]" titleN="Музыка и звук"/>
                        <Legend :data="[]" titleN="Пение"/>
                        <Legend :data="[]" titleN="Хореография(танцы)"/>
                        <Legend :data="[]" titleN="Зрелищные искусства"/>
                        <Legend :data="[]" titleN="Мода и стиль"/>
                        <Legend :data="[]" titleN="Познавательные развлечения"/>
                        <Legend :data="[]" titleN="Туризм"/>
                        <Legend :data="[]" titleN="Естественные науки"/>
                        <Legend :data="[]" titleN="Люди и животные"/>
                        <Legend :data="[]" titleN="Эстетические виды спорта"/>
                        <Legend :data="[]" titleN="Технические виды спорта"/>
                        <Legend :data="[]" titleN="Командно-игровой спорт"/>
                        <Legend :data="[]" titleN="Индивидуально игровой спорт"/>
                        <Legend :data="[]" titleN="Водные виды спорта"/>
                        <Legend :data="[]" titleN="Лёгкая атлетика и гимнастика"/>
                        <Legend :data="[]" titleN="Физкультура"/>




                        
                     </div>
                     
                        
            </div>
     
    </div>
  </template>
  
  <script>
  
  export default {
    data() {
      return {
        selectedAge: '',
        ageOptions: Array.from({ length: 13 }, (_, i) => i + 6), 
      }
    },
  }
  </script>
  
  <style scoped>

.filters{
    width:330px;
    padding:24px;
    
}

  select {
    margin-top: 10px;
    width: 100%;
    padding: 10px;
    border-radius: 5px;
    border: none;
    border-bottom: #70232F 2px solid;  
    font-family: 'Montserrat', sans-serif;
}
  .header{
    font-weight: bold;
    font-size: 24px;
    margin-bottom: 20px;
  }
  .mainF{
    background-color: white;
    padding:10px 20px;
    border-radius: 5px;
    border-top: #70232F 3px solid;

  }

  .age{
    font-weight: bold;
    font-size: 14px;
  }

  .gender{
    margin-top: 15px;
    margin-bottom: 15px;
  }


  input[type="checkbox"] {
    width: 16px;
  height: 16px;
  margin-left: 0;
  cursor: pointer;
  accent-color: #70232F;
  border-radius: 5px;

}


  .genderH{
    margin-bottom:5px;
    font-family: 'Montserrat', sans-serif;
    font-weight: bold;
    font-size: 14px;

  }
  .genders{
    display:flex;
    gap:20px;
    align-items: center;
  }
  .cata{
    margin-bottom:15px;
    font-weight: bold;

  }

  .legends{
    display:flex;
    flex-direction: column;
    gap:15px;
  }
  </style>