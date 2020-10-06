<template>
  <div class="parcoursPage">
    <header>
        <div class="btnMenu" v-on:click="switchInMenu()">
          <div class="barre-hamburger"></div>
          <div class="barre-hamburger"></div>
          <div class="barre-hamburger"></div>
        </div>
    </header>
    <div class="title">
      <h1>Mon parcours</h1>
    </div>
    
    <section class="timeline">
      <ul>
        <li>
            <div>
            <time>
                <p>2015-2018 - Bac S SI</p>
            </time>
            <p>
                J'ai effectué un Bac Scientifique option Sciences de l'Ingénieur au lycée Le Corbusier à Illkirch. 
                J'ai par ailleurs suivi l'option M-SIAD (Métiers des Sciences de l'Innovation de l'Artchitecture et du Design) durant mon année de seconde.
            </p>
            <a href="https://www.lyceelecorbusier.eu/" target="_blank"><h5>Site web de l'établissement</h5></a>
            </div>
        </li>
        <li>
            <div>
            <time>
                <p>2018-2020 - DUT Informatique</p>
            </time>
            <p>
                Je me suis ensuite tourné vers le secteur de l'informatique en choisissant l'IUT Robert Schuman à Illkirch,
                domaine dans lequel j'ai toujours éprouvé un fort intérêt, pour poursuivre mes études. J'ai aussi dû durant cette période
                réalisé un stage de 11 semaines à l'agence web 
                <a href="https://www.dnconsultants.fr/" target="_blank" style="font-weight: bold; font-size: 14px;">DN Consultants</a> situé à Strasbourg.
                Ce stage m'a permit d'avoir une première expérience professionnelle dans le développement web, domaine que j'affectais particulièrement. 
            </p>
            <a  href="https://iutrs.unistra.fr/formation/dut/dut-informatique" target="_blank"><h5>Site web de la formation</h5></a>
            </div>
        </li>
        <li>
            <div>
            <time>
                <p>2020-2021 - Licence Pro CDAD</p>
            </time>
            <p>
                Puis je me suis spécialisé dans le développement web et d'applications en intégrant la Licence Professionnelle CDAD
                (Conception et Développement d'Applications Distribuées) de l'IUT Robert Schuman à Illkirch. Je suis en train de faire cette licence en 
                alternance dans l'agence web 
                <a href="https://www.dnconsultants.fr/" target="_blank" style="font-weight: bold; font-size: 14px;">DN Consultants</a> situé à Strasbourg.
            </p>
            <a  href="https://iutrs.unistra.fr/formation/licence-professionnelle/informatique/cdad" target="_blank"><h5>Site web de la formation</h5></a>
            </div>
        </li>
      </ul>
    </section>
  </div>
</template>

<script>

export default {
  name: 'ParcoursPage',
  data: function() {
    return{
      lol: 1,
      items: []
    }
  },
  mounted(){
    this.items = document.querySelectorAll(".timeline li");

    window.addEventListener("load", this.callbackFunc);
    window.addEventListener("resize", this.callbackFunc);
    window.addEventListener("scroll", this.callbackFunc);
  },
  methods: {
    isElementInViewport(el) {
      var rect = el.getBoundingClientRect();
      return (
        rect.top >= 0 &&
        rect.left >= 0 &&
        rect.bottom <= (window.innerHeight || document.documentElement.clientHeight) &&
        rect.right <= (window.innerWidth || document.documentElement.clientWidth)
      );
    },
    callbackFunc() {
      for (var i = 0; i < this.items.length; i++) {
        if (this.isElementInViewport(this.items[i])) {
        this.items[i].classList.add("in-view");
        }
      }
    },
    switchInMenu() {
      console.log('cool');
      this.$emit('back');
    }
  }
}
</script>

<style scoped>

*,
*::before,
*::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.parcoursPage{
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  /* overflow: hidden; */
  z-index: 3;
}
header{
  width: 100%;
  display: flex;
  justify-content: flex-end;
  align-items: center;
  height: 20vh;
}
.title {
  font-size: 30px;
  height: 20vh;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  align-items: flex-end;
  z-index: 3;
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

/* TIMELINE
–––––––––––––––––––––––––––––––––––––––––––––––––– */
.timeline {
    color: white;
    margin-top: 10vh;

}
.timeline ul {
  background: #cbd6e7;
  padding: 50px 0;

}
.timeline ul li {
  list-style-type: none;
  position: relative;
  width: 6px;
  margin: 0 auto;
  padding-top: 50px;
  background: #cbd6e7;
}
.timeline ul li::after {
  content: '';
  position: absolute;
  left: 50%;
  bottom: 0;
  transform: translateX(-50%);
  width: 30px;
  height: 30px;
  border-radius: 50%;
  background: inherit;
}
.timeline ul li div {
  position: relative;
  bottom: 0;
  width: 400px;
  padding: 15px;
  background: #29ABE2;
  /* background-color: #446491; */
}
.timeline ul li div::before {
  content: '';
  position: absolute;
  bottom: 7px;
  width: 0;
  height: 0;
  border-style: solid;
}
.timeline ul li:nth-child(even) div {
  left: 45px;
}
.timeline ul li:nth-child(even) div::before {
  left: -15px;
  border-width: 8px 16px 8px 0;
  border-color: transparent #29ABE2 transparent transparent;
}
.timeline ul li:nth-child(odd) div {
  left: -439px;
}
.timeline ul li:nth-child(odd) div::before {
  right: -15px;
  border-width: 8px 0 8px 16px;
  border-color: transparent transparent transparent #29ABE2;
}
.timeline time {
  font-size: 1.2rem;
  font-weight: bold;
  margin-bottom: 8px;
  display: flex;
  align-items: center;
}
.timeline a{
  color: white;
}

.timeline li>div>p{
  margin-bottom: 10px;
}

/* EFFECTS
–––––––––––––––––––––––––––––––––––––––––––––––––– */

.timeline ul li::after {
  transition: background .5s ease-in-out;
}
.timeline ul li.in-view::after {
  /* background: #29ABE2; */
  background-color: #446491;
}
.timeline ul li div {
  visibility: hidden;
  opacity: 0;
  transition: all .5s ease-in-out;
}
.timeline ul li:nth-child(odd) div {
  transform: translate3d(200px, 0, 0);
}
.timeline ul li:nth-child(even) div {
  transform: translate3d(-200px, 0, 0);
}
.timeline ul li.in-view div {
  transform: none;
  visibility: visible;
  opacity: 1;
}

/* GENERAL MEDIA QUERIES
–––––––––––––––––––––––––––––––––––––––––––––––––– */

@media screen and (max-width: 900px) {
  .timeline ul li div {
    width: 250px;
  }
  .timeline ul li:nth-child(even) div {
    left: -289px;
    /*250+45-6*/
  }
}
@media screen and (max-width: 600px) {
  .timeline ul li {
    margin-left: 20px;
  }
  .timeline ul li div {
    width: calc(100vw - 91px);
  }
  .timeline ul li:nth-child(even) div {
    left: 45px;
  }
  .timeline ul li:nth-child(even) div::before {
    left: -15px;
    border-width: 8px 16px 8px 0;
    border-color: transparent #29ABE2 transparent transparent;
  }
}
</style>
