<template>
  <div class="competencesPage">
    <header>
      <div class="btnMenu" v-on:click="switchInMenu()">
        <div class="barre-hamburger"></div>
        <div class="barre-hamburger"></div>
        <div class="barre-hamburger"></div>
      </div>
    </header>
    <div class="title">
      <h1>Compétences</h1>
    </div>
    <div class="container-card">
      <card-language class="card-container" v-for="card in listCards"
        :key="card.title"
        :title="card.title"
        :imgUrl="card.imgUrl"
        :wikipedia="card.wikipedia"
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
        { 
          title: "HTML",
          imgUrl: 'https://www.w3.org/html/logo/downloads/HTML5_Logo_512.png',
          description: '',
          wikipedia: 'https://fr.wikipedia.org/wiki/HTML5'
        },
        { 
          title: "CSS", 
          imgUrl: 'https://upload.wikimedia.org/wikipedia/commons/thumb/d/d5/CSS3_logo_and_wordmark.svg/1200px-CSS3_logo_and_wordmark.svg.png',
          description: '',
          wikipedia: 'https://fr.wikipedia.org/wiki/Feuilles_de_style_en_cascade'  
        },
        { 
          title: "JS", 
          imgUrl: 'https://upload.wikimedia.org/wikipedia/commons/thumb/b/b6/Badge_js-strict.svg/555px-Badge_js-strict.svg.png',
          description: '',
          wikipedia: 'https://fr.wikipedia.org/wiki/JavaScript'  
        },
        { 
          title: 'Bootstrap', 
          imgUrl: 'https://sdtimes.com/wp-content/uploads/2018/01/bootstrap-stack.png',
          description: '',
          wikipedia: 'https://fr.wikipedia.org/wiki/Bootstrap_(framework)'
        },
        { 
          title: "Node", 
          imgUrl: 'https://upload.wikimedia.org/wikipedia/commons/thumb/d/d9/Node.js_logo.svg/1200px-Node.js_logo.svg.png',
          description: '',
          wikipedia: 'https://fr.wikipedia.org/wiki/Node.js'
        },
        { 
          title: "Vue", 
          imgUrl: 'https://upload.wikimedia.org/wikipedia/commons/thumb/9/95/Vue.js_Logo_2.svg/1200px-Vue.js_Logo_2.svg.png',
          description: '',
          wikipedia: 'https://fr.wikipedia.org/wiki/Vue.js'
        },
        { 
          title: "React", 
          imgUrl: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/a7/React-icon.svg/1200px-React-icon.svg.png',
          description: '',
          
          wikipedia: 'https://fr.wikipedia.org/wiki/React_(JavaScript)'  
        },
        { 
          title: "PHP", 
          imgUrl: 'https://upload.wikimedia.org/wikipedia/commons/thumb/2/27/PHP-logo.svg/1280px-PHP-logo.svg.png',
          description: '',
          
          wikipedia: 'https://fr.wikipedia.org/wiki/PHP' 
        },
        { 
          title: "Symfony", 
          imgUrl: 'https://cdn.freebiesupply.com/logos/thumbs/2x/symfony-logo.png',
          description: '',
          wikipedia: 'https://fr.wikipedia.org/wiki/Symfony'
        },
        { 
          title: "Python", 
          imgUrl: 'https://upload.wikimedia.org/wikipedia/commons/thumb/c/c3/Python-logo-notext.svg/1200px-Python-logo-notext.svg.png',
          description: '',
          wikipedia: 'https://fr.wikipedia.org/wiki/Python_%28langage%29'
        },
        { 
          title: "Java", 
          imgUrl: 'https://www.softexia.com/wp-content/uploads/2017/04/Java-logo.png',
          description: '',
          
          wikipedia: 'https://fr.wikipedia.org/wiki/Java_(technique)'
        },
        { 
          title: "Android Studio", 
          imgUrl: 'https://appjoy.org/wp-content/uploads/2016/05/Android-Studio-Logo.png',
          description: '',
          wikipedia: 'https://fr.wikipedia.org/wiki/Android_Studio'
        },
        { 
          title: "PL/SQL", 
          imgUrl: 'https://metamug.com/article/images/pl-sql-database.jpg',
          description: '',
          wikipedia: 'https://fr.wikipedia.org/wiki/PL/SQL'
        },
        { 
          title: "C#", 
          imgUrl: 'https://www.onlinebooksreview.com/uploads/blog_images/2018/01/27_c-sharp-logo-filled.png',
          description: '',
          wikipedia: 'https://fr.wikipedia.org/wiki/C_sharp'
        },
        { 
          title: "Bash", 
          imgUrl: 'https://raw.githubusercontent.com/odb/official-bash-logo/master/assets/Logos/Icons/PNG/512x512.png',
          description: '',
          wikipedia: 'https://fr.wikipedia.org/wiki/Bourne-Again_shell'
        },
        { 
          title: "Git", 
          imgUrl: 'https://git-scm.com/images/logos/downloads/Git-Icon-Black.png',
          description: '',
          wikipedia: 'https://fr.wikipedia.org/wiki/Git'
        }
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
  height: 30vh;
}
header .btnMenu{
  z-index: 3;
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
  animation-duration: 1s;
  margin-top: 10px;
  width: 66%;
}
.title{
  margin-top: 2vh;
  margin-left: 5vw;
  font-size: 30px;
  z-index: 3;
}
.container-card{
  /* border: solid red; */
  margin-top: 5vh;
  margin-left: 5vw;
  width: 70%;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  /* height: 20vh; */
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