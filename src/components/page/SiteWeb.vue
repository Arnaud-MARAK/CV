<template>
  <body>

    <transition-page class="page" v-if="showTransition" ref="transition" />

    <div v-if="showMenu" class="menuPage">
      <nav>
        <ul>
          <li v-on:click="switchInIndex()">Accueil</li>
          <li v-on:click="switchInParcours()">Parcours</li>
          <li v-on:click="switchInCompetences()">Compétences</li>
          <!-- <li>Projets</li> -->
          <li v-on:click="switchInContact()">Contact</li>
        </ul>
      </nav>
    </div>

    <index-page v-if="showIndex" @back="switchInMenuFromIndex"/>

    <parcours-page v-if="showParcours" @back="switchInMenuFromParcours"/>

    <competences-page v-if="showCompetences" @back="switchInMenuFromCompetences"/>

    <contact-page v-if="showContact" @back="switchInMenuFromContact"/>
  </body>
</template>

<script>
import TransitionPage from './TransitionPage.vue';
import IndexPage from './IndexPage.vue';
import ParcoursPage from './ParcoursPage.vue';
import CompetencesPage from './CompetencesPage.vue';
import ContactPage from './ContactPage.vue';

export default {
  name: 'SiteWeb',
  components: {
    TransitionPage,
    IndexPage,
    ParcoursPage,
    CompetencesPage,
    ContactPage
  },
  data: function() {
    return{
      widthPage: window.innerWidth,
      heightPage: window.innerHeight,
      showTransition: true,
      showMenu: false,
      showIndex: false,
      showParcours: false,
      showCompetences: false,
      showContact: false
    }
  },
  mounted(){
    // this.switchInIndex()
    // this.switchInParcours()
    // this.switchInCompetences()
    this.switchInContact()
  },
  methods: {
    switchInMenuFromIndex(){
      this.$refs.transition.switchInMenuFromIndex()
      this.showIndex = false
      this.showMenu = true
    },
    switchInMenuFromParcours(){
      this.$refs.transition.switchInMenuFromParcours()
      this.showParcours = false
      this.showMenu = true
    },
    switchInMenuFromCompetences(){
      this.$refs.transition.switchInMenuFromCompetences()
      this.showCompetences = false
      this.showMenu = true
    },
    switchInMenuFromContact(){
      this.$refs.transition.switchInMenuFromContact()
      this.showContact = false
      this.showMenu = true
    },
    switchInIndex(){
      this.$refs.transition.switchInIndex()
      this.showMenu = false
      this.showIndex = true
    },
    switchInParcours(){
      this.$refs.transition.switchInParcours()
      this.showMenu = false
      this.showParcours = true
    },
    switchInCompetences(){
      this.$refs.transition.switchInCompetences()
      this.showMenu = false
      this.showCompetences = true
    },
    switchInContact(){
      this.$refs.transition.switchInContact()
      this.showMenu = false
      this.showContact = true
    }
  }
}
</script>

<style scoped>
  body{
    background-color: #f5eded;
    /* background-color: white; */
    font-family: 'Bookman', sans-serif;
    overflow-x: hidden;
  }

  .page{
    position: absolute;
  }
  /**************/
  /* MENU PAGE */
  /**************/

  .menuPage{
    width: 99vw;
    height: 100vh;
    position: absolute;
    color: white;
    font-size: 25px;
    font-weight: bold;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .menuPage ul{
    display: flex;
    flex-direction: column;
    align-items: center;
    color: #f5eded;
  }
  .menuPage li:hover{
    border-bottom: solid white;
    /* animation-name: animationNav; */
    animation-duration: 2s;
    animation-iteration-count: infinite;
    animation-timing-function: ease-in;
  }


@keyframes animationNav{
  0%{
    border-bottom: solid black;
  }
  5%{
    border-bottom: solid white;
  }
  100%{
    border-bottom: solid black;
  }
}
@keyframes hoverCards{
    0%{
        transform: translateY(0px);
    }
    25%{
        transform: translateY(-10px);
    }
    50%{
        transform: translateY(0px);
    }
    75%{
        transform: translateY(10px);  
    }
    100%{
        transform: translateY(0px);
    }
}

@media (max-width: 680px) {
  .menuPage{
    font-size: 17px;
  }
}

@media (min-width: 681px) and (max-width: 1279px) {
  .menuPage{
    font-size: 23px;
  }
}

@media (min-width: 1280px) {
  .menuPage{
    font-size: 25px;
  }
}
</style>
