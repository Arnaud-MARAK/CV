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
    /* border: solid red; */
    margin-left: 10vw;
    margin-top: 5vh;
  }
  header .btnMenu{
    /* border: solid red; */
    background-size: cover;
    margin-right: 5vw;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  .barre-hamburger{
    width: 100%;
  }
  header .btnMenu:hover > .barre-hamburger{
      animation-duration: 0.8s;
      animation-timing-function: ease;
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

  @keyframes animationHamburgerSmall{
    0%{
      margin-top: 7px;
      width: 100%;
    }
    100%{
      margin-top: 5px;
      width: 66%;
    }
  }

  @media (max-width: 680px) {
    h1{
      font-size: 30px;
    }
    h2{
      font-size: 20px;
      margin-top: 12vh;
      margin-left: 12vw;
    }
    header{
      align-items: flex-start;
    }
    header .titles{
      margin-top: 12vh;
    }
    header .btnMenu{
      width: 40px;
      margin-right: 5vw;
      margin-top: 4vh;
    }
    .barre-hamburger{
      border-top: 2px solid black;
      margin-top: 7px;
    }
    header .btnMenu:hover > .barre-hamburger{
      animation-name: animationHamburgerSmall;
      margin-top: 5px;
      width: 66%;
    }
  }

  @media (min-width: 681px) and (max-width: 1279px) {
    h1{
      font-size: 40px;
    }
    h2{
      font-size: 28px;
      margin-top: 12vh;
      margin-left: 12vw;
    }
    header .btnMenu{
      width: 45px;
      margin-left: 4vw;
    }
    .barre-hamburger{
      border-top: 4px solid black;
      margin-top: 15px;
    }
    header .btnMenu:hover > .barre-hamburger{
      animation-name: animationHamburger;
      margin-top: 10px;
      width: 66%;
    }
  }

  @media (min-width: 1280px) {
    h1{
      font-size: 50px;
    }
    h2{
      font-size: 35px;
      margin-top: 12vh;
      margin-left: 12vw;
    }
    header .btnMenu{
      width: 50px;
    }
    .barre-hamburger{
      border-top: 4px solid black;
      margin-top: 15px;
    }
    header .btnMenu:hover > .barre-hamburger{
      animation-name: animationHamburger;
      margin-top: 10px;
      width: 66%;
    }
  }

</style>
