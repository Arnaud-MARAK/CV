<template>
  <li class="card">
    <h3 class="title-card">{{title}}</h3>
    <img class="img-card" :src="imgUrl" alt="card competence">
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
  },
  created(){
    // console.log(window.location.pathname)
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.card{
  width: 150px;
  height: 200px;
  background-color: #f4a261;
  margin: 5px;
  display: flex;
  flex-direction: column;
  /* justify-content: center; */
  align-items: center;
}
.title-card{
  margin-top: 10px;
}
.img-card{
  border: solid red;
  margin-top: 20px;
  width: 120px;
  height: 120px;
}
</style>
