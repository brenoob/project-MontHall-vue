<template>
  <div id="app">
    <h1>Problema de monty hall</h1>
    <div class="form">
      <div v-if="!started">
        <label for="doorAmount">Quantas portas</label>
        <input type="text" id="doorAmount" size="3" v-model.number="doorAmount">
      </div>
      <div v-if="!stated">
        <label for="selectedDoor">Qual a porta premiada?</label>
        <input type="text" id="selectedDoor" size="3" v-model.number="selectedDoor">
      </div>
      <button v-if="!started" @click="started = true">Iniciar</button>
      <button v-if="started" @click="started = false">Reiniciar</button>
    </div>
    <div class="doors" v-if="started">
      <div v-for="i in doorAmount" :key="i">
        <Door :hasGift="i === selectedDoor" :number="i" />
      </div>
    </div>
  </div>
</template>

<script>
import Door from './components/Door.vue'
export default {
  name:'App',
  components: { Door },
  data() {
    return{
      started:false,
      doorAmount:3,
      selectedDoor:null
    }
  }
};
</script>

<style>
* {
  box-sizing: border-box;
  font-family: Montserrat, sans-serif;
}
body {
  background: linear-gradient(
    90deg,
    hsla(339, 100%, 55%, 0.8) 0%,
    hsla(197, 100%, 64%, 1) 100%
  );
  color: #fff;
}
#app{
  display: flex;
  flex-direction: column;
  align-items: center;
}
#app h1 {
  border: 1px solid #000;
  background-color: #0004;
  padding: 20px;
  margin-bottom: 60px;
}
.form{
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin-bottom: 40px;
}
.form, .form input, .form button {
  margin-bottom: 10px;
  font-size: 2rem;
}
.doors{
  align-self: stretch;
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
}
</style>