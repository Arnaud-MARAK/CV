<template>
  <div class="indexPage">
    <header>
      <div class="titles">
        <h1>Arnaud Marak</h1>
        <h2>Développeur Web et Application Distribuées</h2>
      </div>
      <div class="btnMenu" v-on:click="switchInMenu()">
        <div class="barre-hamburger"></div>
        <div class="barre-hamburger"></div>
        <div class="barre-hamburger"></div>
      </div>
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
    /* width: 100vw; */
    /* height: 100vh; */
    position: absolute;
    top: 0;
    overflow: hidden;
  }
  header{
    width: 99vw;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  header .titles{
    margin-left: 10vw;
    margin-top: 5vh;
  }
  h1{
    font-size: 50px;
  }
  h2{
    font-size: 35px;
    margin-top: 4vh;
    margin-left: 10vw;
  }
  header .btnMenu{
    width: 60px;
    background-size: cover;
    margin-right: 5vw;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  .barre-hamburger{
    width: 50px;
    border-top: 4px solid black;
    margin-top: 15px;
  }
  header .btnMenu:hover > .barre-hamburger{
    animation-name: animationHamburger;
    animation-duration: 0.8s;
    animation-timing-function: ease;
    margin-top: 10px;
    width: 66%;
  }
  @keyframes animationHamburger{
    0%{
      margin-top: 15px;
      width: 100%;
    }
    100%{
      margin-top: 10px;
      width: 66%;
    }
  }
</style>
