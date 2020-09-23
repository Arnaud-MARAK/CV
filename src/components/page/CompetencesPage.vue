<template>
  <div class="competencesPage">
    <header>
      <div class="btnMenu" v-on:click="switchInMenu()"/>
    </header>
    <h1>Compétences</h1>
    <h1>TEST
    azbnd azid azboibazejd bazfobe fmjzaeb ofzeb fezba fuozebf uazeb fkmjzf p
    zda *azmdzak dpoazjd poazj piaznfpiazhfioâz bfs
    b</h1>
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
*{
  margin: 0;
  padding: 0;
}

.competencesPage{
  display: flex;
  flex-direction: column;
  align-items: center;
}
header{
  width: 100%;
  display: flex;
  justify-content: flex-end;
  align-items: center;
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
</style>