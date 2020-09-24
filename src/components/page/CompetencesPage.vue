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
        { title: "HTML", imgUrl: 'https://www.w3.org/html/logo/downloads/HTML5_Logo_512.png' },
        { title: "CSS", imgUrl: 'https://upload.wikimedia.org/wikipedia/commons/thumb/d/d5/CSS3_logo_and_wordmark.svg/1200px-CSS3_logo_and_wordmark.svg.png' },
        { title: "JS", imgUrl: 'https://upload.wikimedia.org/wikipedia/commons/thumb/b/b6/Badge_js-strict.svg/555px-Badge_js-strict.svg.png' },
        { title: "Node", imgUrl: 'https://upload.wikimedia.org/wikipedia/commons/thumb/d/d9/Node.js_logo.svg/1200px-Node.js_logo.svg.png' },
        { title: "Vue", imgUrl: 'https://upload.wikimedia.org/wikipedia/commons/thumb/9/95/Vue.js_Logo_2.svg/1200px-Vue.js_Logo_2.svg.png' },
        { title: "React", imgUrl: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/a7/React-icon.svg/1200px-React-icon.svg.png' },
        { title: "PHP", imgUrl: 'https://upload.wikimedia.org/wikipedia/commons/thumb/2/27/PHP-logo.svg/1280px-PHP-logo.svg.png' },
        { title: "Symfony", imgUrl: 'https://cdn.freebiesupply.com/logos/thumbs/2x/symfony-logo.png' },
        { title: "Python", imgUrl: 'https://upload.wikimedia.org/wikipedia/commons/thumb/c/c3/Python-logo-notext.svg/1200px-Python-logo-notext.svg.png' },
        { title: "Java", imgUrl: 'https://www.softexia.com/wp-content/uploads/2017/04/Java-logo.png' },
        { title: "PL/SQL", imgUrl: 'https://metamug.com/article/images/pl-sql-database.jpg' },
        { title: "C#", imgUrl: 'https://www.onlinebooksreview.com/uploads/blog_images/2018/01/27_c-sharp-logo-filled.png'}
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
  /* border: solid red; */
  margin-top: 5vh;
  margin-left: 12vw;
  width: 70%;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  /* height: 20vh; */
}
</style>