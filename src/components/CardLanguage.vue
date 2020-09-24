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
    console.log(this.imgUrl)
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.card{
  z-index: 3;
  width: 150px;
  height: 200px;
  background-color: #f4a261;
  color: white;
  border-radius: 3px;
  margin: 10px;
  display: flex;
  flex-direction: column;
  /* justify-content: center; */
  align-items: center;
}
.title-card{
  margin-top: 10px;
}
.img-card{
  margin-top: 20px;
  width: 120px;
  height: 120px;
  object-fit: contain;
}
.card:hover{
  background-color: orange;
}
</style>
