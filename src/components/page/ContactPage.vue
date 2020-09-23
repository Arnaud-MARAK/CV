<template>
  <div class="contactPage">
    <header>
      <div class="title">
        <h1>Contact</h1>
      </div>
      <div class="btnMenu" v-on:click="switchInMenu()"/>
    </header>
    <div class="remplisseur">
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
  justify-content: flex-end;
  align-items: center;
  height: 20vh;
  width: 100vw;
}
header .btnMenu{
  z-index: 3;
  width: 40px;
  height: 40px;
  background-image: url('../../assets/img/menu.png');
  background-size: cover;
  margin-right: 4vw;
}
.title {
  font-size: 30px;
  height: 10vh;
  margin-right: 35vw;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  aligne-items: flex-end;
}
.remplisseur{
  height: 70vh;
  width: 99vw;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.remplisseur p{
  font-size: 20px;
  margin-top: 5vh;
}
.remplisseur button{
  background-color: #94D5F1;
  border: none;
  border-radius: 3px;
  font-size: 15px;
  font-weight: bold;
  height: 6vh;
  margin: 2vh 0 0 0;
  padding: 1vh 1vw;
}
.remplisseur button:hover{
  background-color: #bbe5f6;
}

</style>