<template>
  <div class="competencesPage">
    <header>
      <div class="btnMenu" v-on:click="switchInMenu()"/>
    </header>
    <h1>Compétences</h1>
    <div class="container-card">
      <card-language class="card-container" v-for="card in listCards"
        :key="card.title"
        :title="card.title"
        :imgUrl="card.imgUrl"
      ></card-language>
    </div>
  </div>
</template>

<script>

import CardLanguage from '../CardLanguage.vue';

export default {
  name: 'ContactPage',
  components: {
    CardLanguage
  },
  data: function() {
    return{
      listCards: [
        { title: "Python", imgUrl: '../assets/img/python.png' },
        { title: "Java", imgUrl: '../assets/img/java.png' }
      ]
    }
  },
  methods: {
    switchInMenu() {
      this.$emit('back');
    }
  }
}
</script>

<style scoped>
*{
  margin: 0;
  padding: 0;
}

.competencesPage{
  display: flex;
  flex-direction: column;
  align-items: center;
  /* border: solid black; */
}
header{
  display: flex;
  justify-content: flex-end;
  align-items: center;
  width: 100%;
  height: 20vh;
}
header .btnMenu{
  z-index: 3;
  width: 40px;
  height: 40px;
  background-image: url('../../assets/img/menu.png');
  background-size: cover;
  margin-right: 5vw;
}
h1{
  margin-top: 2vh;
  width: 5vw;
}
.container-card{
  border: solid red;
  margin-top: 5vh;
  margin-left: 12vw;
  width: 70%;
  display: flex;
  /* height: 20vh; */
}
</style>