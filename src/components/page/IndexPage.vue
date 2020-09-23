<template>
  <div class="indexPage">
    <header>
      <div class="titles">
        <h1>Arnaud Marak</h1>
        <h2>Développeur Web et Application Distribuées</h2>
      </div>
      <div class="btnMenu" v-on:click="switchInMenu()"/>
    </header>
  </div>
</template>

<script>

export default {
  name: 'IndexPage',
  methods: {
    switchInMenu() {
      this.$emit('back');
    }
  }
}
</script>

<style scoped>
  .indexPage{
    width: 100vw;
    /* height: 100vh; */
    position: absolute;
    top: 0;
    overflow: hidden;
  }
  header{
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  header .titles{
    margin-left: 10vw;
    margin-top: 5vh;
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
    font-size: 50px;
  }
  h2{
    font-size: 35px;
    margin-top: 4vh;
    margin-left: 10vw;
  }
</style>
