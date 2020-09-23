<template>
  <div id="app">
    <site-web />
  </div>
</template>

<script>
// import CardLanguage from './components/CardLanguage.vue'
import SiteWeb from './components/page/SiteWeb.vue'

export default {
  name: 'App',
  components: {
    SiteWeb
  },
  data: function() {
    return{
      listLanguage: [
        { id: 0, name: 'Java', imgUrl: '../assets/img/java.png' },
        { id: 1, name: 'Python', imgUrl: '../assets/img/java.png' },
        { id: 2, name: 'C#', imgUrl: '../assets/img/java.png' },
        { id: 3, name: 'PL/SQL', imgUrl: '../assets/img/java.png' }
      ]
    }
  }
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
}
li{
  list-style: none;
  margin: 20px;
}

</style>
