<template>
  <div class="home">
    <div class="cards__container"> 
      <div class="card-flex" v-for="good,index in goods" :key="index" >
        <div class="cad-img" :style="{ backgroundImage: 'url('+ good.src+')' }"></div>
        <div class="good__container">
        <h1>{{good.title}}</h1>
        <p>{{good.about}}</p>
        <h3>{{good.price}}</h3>
        <button class="btn" @click="targetGood = index">Заказать</button>
        </div>
      </div>
    </div>
    <contactForm :data="targetGood ==-1 ? {title:'Товар не выбран'} : goods[targetGood]" v-if="targetGood != -1" @close="closeForm()"/>  
  </div>
</template>

<script>
import contactForm from '@/components/contactForm.vue'

export default {
  name: 'home',
  data() {
    return {

      goods: [
        { 
          title:'Кеды ElGrande', 
          src:require('@/assets/img/ced.jpeg'),
          about:'Самые прыгучие',
          price: '3400 ₽'
        },
         { 
          title:'Кеды Billioner', 
          src:require('@/assets/img/ced2.jpeg'),
          about:'Самые большие',
          price: '5000 ₽'
        },
         { 
          title:'Кеды Shmups', 
          src:require('@/assets/img/ced3.jpeg'),
          about:'Самые креативные',
          price: '4300 ₽'
        },
         { 
          title:'Кеды Fainar', 
          src:require('@/assets/img/ced4.jpeg'),
          about:'Самые роскошные',
          price: '100000 ₽'
        }  
      ],
      targetGood: -1
    }
  },
  methods: {
    closeForm() {
      this.targetGood = -1
    }
  },

  components: {
    contactForm
  }
}
</script>

<style scoped>
.cad-img {
  height: 248px;
  width: 100%;
  background-repeat: no-repeat;
  background-size: contain;
}
.cards__container {
  height: 100%;
  width: 100%;
  display: flex;
  align-content: center;
  justify-content: center;
  gap: 20px;
  padding-top: 60px;
  margin-bottom: 60px;
}
.card-flex {
  height: 420px;
  width: 248px;
  border: 1px solid gold;
}
.good__container {
  margin-top: 20px;
}
.btn {
  background-color: #fff000;
  border-radius: 0;
  color: #000;
  cursor: pointer;
  font-weight: bold;
  padding: 10px 15px;
  text-align: center;
  transition: 200ms;
  width: 100%;
  box-sizing: border-box;
  border: 0;
  font-size: 16px;
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
}

.btn:not(:disabled):hover,
.btn:not(:disabled):focus {
  outline: 0;
  background: #f4e603;
  box-shadow: 0 0 0 2px rgba(0,0,0,.2), 0 3px 8px 0 rgba(0,0,0,.15);
}

.btn:disabled {
  filter: saturate(0.2) opacity(0.5);
  -webkit-filter: saturate(0.2) opacity(0.5);
  cursor: not-allowed;
}


</style>