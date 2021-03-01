<template>
  <body>
    <transition-page class="page" v-if="showTransition" ref="transition" />

    <div v-if="showMenu" class="menuPage">
      <nav>
        <ul>
          <li class="elem-menu fill-effect" v-on:click="switchInIndex()">
            <p class="fill-effect-stroke">Accueil</p>
            <p class="fill-effect-fill">Accueil</p>
          </li>
          <li class="elem-menu fill-effect" v-on:click="switchInParcours()">
            <p class="fill-effect-stroke">Parcours</p>
            <p class="fill-effect-fill">Parcours</p>
          </li>
          <li class="elem-menu fill-effect" v-on:click="switchInCompetences()">
            <p class="fill-effect-stroke">Compétences</p>
            <p class="fill-effect-fill">Compétences</p>
          </li>
          <li class="elem-menu fill-effect" v-on:click="switchInContact()">
            <p class="fill-effect-stroke">Contact</p>
            <p class="fill-effect-fill">Contact</p>
          </li>
        </ul>
      </nav>
    </div>

    <index-page v-if="showIndex" @back="switchInMenuFromIndex" />

    <parcours-page v-if="showParcours" @back="switchInMenuFromParcours" />

    <competences-page
      v-if="showCompetences"
      @back="switchInMenuFromCompetences"
    />

    <contact-page v-if="showContact" @back="switchInMenuFromContact" />
  </body>
</template>

<script>
import TransitionPage from "./TransitionPage.vue";
import IndexPage from "./IndexPage.vue";
import ParcoursPage from "./ParcoursPage.vue";
import CompetencesPage from "./CompetencesPage.vue";
import ContactPage from "./ContactPage.vue";

export default {
  name: "SiteWeb",
  components: {
    TransitionPage,
    IndexPage,
    ParcoursPage,
    CompetencesPage,
    ContactPage,
  },
  data: function () {
    return {
      widthPage: window.innerWidth,
      heightPage: window.innerHeight,
      showTransition: true,
      showMenu: false,
      showIndex: false,
      showParcours: false,
      showCompetences: false,
      showContact: false,
    };
  },
  mounted() {
    this.switchInIndex();
    // this.switchInParcours()
    // this.switchInCompetences();
    // this.switchInContact()
  },
  methods: {
    switchInMenuFromIndex() {
      this.$refs.transition.switchInMenuFromIndex();
      this.showIndex = false;
      this.showMenu = true;
    },
    switchInMenuFromParcours() {
      this.$refs.transition.switchInMenuFromParcours();
      this.showParcours = false;
      this.showMenu = true;
    },
    switchInMenuFromCompetences() {
      this.$refs.transition.switchInMenuFromCompetences();
      this.showCompetences = false;
      this.showMenu = true;
    },
    switchInMenuFromContact() {
      this.$refs.transition.switchInMenuFromContact();
      this.showContact = false;
      this.showMenu = true;
    },
    switchInIndex() {
      document.querySelectorAll("title")[0].textContent = "Accueil";
      this.$refs.transition.switchInIndex();
      this.showMenu = false;
      this.showIndex = true;
    },
    switchInParcours() {
      this.$refs.transition.switchInParcours();
      document.querySelectorAll("title")[0].textContent = "Parcours";
      this.showMenu = false;
      this.showParcours = true;
    },
    switchInCompetences() {
      document.querySelectorAll("title")[0].textContent = "Compétences";
      this.$refs.transition.switchInCompetences();
      this.showMenu = false;
      this.showCompetences = true;
    },
    switchInContact() {
      document.querySelectorAll("title")[0].textContent = "Contact";
      this.$refs.transition.switchInContact();
      this.showMenu = false;
      this.showContact = true;
    },
  },
};
</script>

<style scoped>
body {
  background-color: #f5eded;
  /* background-color: white; */
  font-family: "Helvetica", sans-serif;
  overflow-x: hidden;
}

.page {
  position: absolute;
}
/**************/
/* MENU PAGE */
/**************/

.menuPage {
  width: 99vw;
  height: 100vh;
  position: absolute;
  color: white;
  font-weight: bold;
  display: flex;
  justify-content: center;
  align-items: center;
}
.menuPage ul {
  display: flex;
  flex-direction: column;
  align-items: center;
  color: #f5eded;
}

.stroke-effect {
  -webkit-text-stroke-width: 2px;
  -webkit-text-stroke-color: white;
  color: rgba(255, 255, 255, 0);
  transition: opacity 400ms ease, color 1400ms;
  transition-delay: 0s, 200ms;
  transition-property: opacity, color;
  opacity: 0.5;
}
.stroke-effect:hover {
  opacity: 1;
  color: rgba(255, 255, 255, 1);
}
.fill-effect {
  position: relative;
}
.fill-effect:hover > .fill-effect-stroke {
  visibility: hidden;
}
.fill-effect:hover > .fill-effect-fill {
  clip-path: inset(0 0 0 0);
}
.fill-effect-stroke {
  position: absolute;
  visibility: visible;
  color: rgba(255, 255, 255, 0);
  -webkit-text-stroke-width: 2px;
  -webkit-text-stroke-color: white;
  z-index: 2;
  transition: visibility 0.8s;
}
.fill-effect-fill {
  color: white;
  z-index: 1;
  clip-path: inset(100% 0 0 0);
  transition: clip-path 1600ms ease;
}

@media (max-width: 679px) {
  .elem-menu {
    font-size: 28px;
  }
  .fill-effect-stroke {
    color: white;
    -webkit-text-stroke-width: 0px;
  }
}

@media (min-width: 680px) and (max-width: 1299px) {
  .elem-menu {
    font-size: 42px;
  }
  .fill-effect-stroke {
    -webkit-text-stroke-width: 1px;
  }
}

@media (min-width: 1300px) and (max-width: 1799px) {
  .elem-menu {
    font-size: 60px;
  }
  .fill-effect-stroke {
    -webkit-text-stroke-width: 2px;
  }
}

@media (min-width: 1800px) {
  .elem-menu {
    color: blue;
  }
  .fill-effect-stroke {
    -webkit-text-stroke-width: 2.5px;
  }
}
</style>
