<template>
  <li class="card">
    <h2>{{imgUrl}}</h2>
    <div class="imgCard"></div>
  </li>
</template>

<script>
export default {
  name: 'CardLanguage',
  props: {
    title: {
      type: String,
      default: ''
    },
    imgUrl: {
      type: String,
      default: ''
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.card{
    width: 250px;
    height: 300px;
    background-color: #ffccff;
}
.imgCard{
  border: solid white;
  width: 100px;
  height: 100px;
  background-image: url('{{imgUrl}}');
  background-size: contain;
  background-repeat: no-repeat;
}
</style>
