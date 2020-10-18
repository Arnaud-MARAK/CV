<template>
  <div class="contactPage">
    <header>
      <div class="title">
        <h1>Contact</h1>
      </div>
      <div class="btnMenu" v-on:click="switchInMenu()">
        <div class="barre-hamburger"></div>
        <div class="barre-hamburger"></div>
        <div class="barre-hamburger"></div>
      </div>
    </header>
    <div class="formulaire">
      <h2>Vous souhaitez me poser une question ou autre ?</h2>
      <p>arnaudmarak@tutanota.com</p>
      <a href="mailto:arnaudmarak@tutanota.com"><button>M'envoyer un mail</button></a>
    </div>
  </div>
</template>

<script>

export default {
  name: 'ContactPage',
  methods: {
    switchInMenu() {
      this.$emit('back');
    }
  }
}
</script>

<style scoped>

.contactPage{
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
header{
  display: flex;
  justify-content: center;
  align-items: center;
  height: 20vh;
  width: 100vw;
  z-index: 3;
}
header .btnMenu{
  position: absolute;
  background-size: cover;
  right: 5vw;
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
.title {
  font-size: 30px;
  height: 10vh;
  /* margin-right: 35vw; */
  /* margin-left: 15vw; */
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  align-items: flex-end;
}
.formulaire{
  height: 70vh;
  width: 99vw;
  display: flex;
  flex-direction: column;
  align-items: center;
  z-index: 3;
}
.formulaire p{
  margin-top: 5vh;
}
.formulaire button{
  background-color: #94D5F1;
  border: none;
  border-radius: 3px;
  font-size: 15px;
  font-weight: bold;
  height: 6vh;
  margin: 2vh 0 0 0;
  padding: 1vh 1vw;
}
.formulaire button:hover{
  background-color: #bbe5f6;
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
    font-size: 16px;
    margin-right: 25vw;
  }
  header .btnMenu{
    width: 25px;
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
  .formulaire {
    margin-left: 3vw;
    align-items: flex-start;
  }
  .formulaire p{
    font-size: 12px;
    margin-top: 5vh;
  }
  .formulaire button{
    font-size: 10px;
    padding: 1vh 2vw;
  }
}

@media (min-width: 681px) and (max-width: 1279px) {
  h1{
    font-size: 40px;
  }
  h2{
    font-size: 20px;
  }
  header .btnMenu{
    width: 45px;
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
  .formulaire p{
    font-size: 18px;
  }
  .formulaire button{
    font-size: 14px;
  }
}

@media (min-width: 1280px) {
  h1{
    font-size: 50px;
  }
  h2{
    font-size: 25px;
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
  .formulaire p{
    font-size: 20px;
  }
  .formulaire button{
    font-size: 15px;
  }
}

</style>