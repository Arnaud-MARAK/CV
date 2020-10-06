<template>
  <div class="webpage">
    <svg class="svgPage" :width="widthPage" :height="heightPage" :max-width="widthPage">

      <!-- LeftBot LeftTop RightTop MidTop RightBot !-->
      <!-- 0,0 0,0 215,110 215,55 !-->
      <polygon class="polymorph" points="215,110 0,110 0,0 47.7,0 215,0"/>
    </svg>
  </div>
</template>

<script>
import anime from 'animejs/lib/anime.es.js';

export default {
  name: 'TransitionPage',
  data: function() {
    return{
      widthPage: window.innerWidth,
      heightPage: window.innerHeight
    }
  },
  methods: {
    switchInMenuFromIndex(){
      anime({
        targets: '.polymorph',
        points: [
          { value: this.widthPage + ',' + this.heightPage + ' 0,' + this.heightPage + ' 0,0 ' + (this.widthPage / 4.5) +',0 ' + (this.widthPage / 3.2) + ',' + (this.heightPage / 1.45)},
          { value: this.widthPage + ',' + this.heightPage + ' 0,' + this.heightPage + ' 0,0 ' + (this.widthPage / 4.5) +',0 ' + this.widthPage + ',0'}
        ],
        easing: 'easeOutQuad',
        duration: 1200,
        loop: false
      });
    },
    switchInMenuFromParcours(){
      anime({
        targets: '.polymorph',
        points: [
          { value: this.widthPage + ',' + this.heightPage + ' ' + (this.widthPage / 1.35) + ',' + (this.heightPage / 3.5) + ' 0,' + this.heightPage / 4 + ' 0,0 ' + this.widthPage + ',0'},
          { value: this.widthPage + ',' + this.heightPage + ' ' + ' 0,' + this.heightPage + ' 0,' + this.heightPage + ' 0,0 ' + this.widthPage + ',0'}
        ],
        easing: 'easeOutQuad',
        duration: 1200,
        loop: false
      });
    },
    switchInMenuFromCompetences(){
      anime({
        targets: '.polymorph',
        points: [
          {value: '0,' + this.heightPage + ' ' + (this.widthPage / 10) + ',' + this.heightPage + ' ' + (this.widthPage / 6) + ',' + (this.heightPage / 7) + ' ' +  this.widthPage + ',' + (this.heightPage / 4) + ' ' + this.widthPage + ',0 0,0'},
          {value: '0,' + this.heightPage + ' ' + (this.widthPage / 10) + ',' + this.heightPage + ' ' + (this.widthPage / 5.2) + ',' + (this.heightPage / 4) + ' ' +  this.widthPage + ',0 ' + this.widthPage + ',0 0,0'},
          {value: '0,' + this.heightPage + ' ' + this.widthPage + ',' + this.heightPage + ' ' + this.widthPage + ',' + this.heightPage + ' ' +  this.widthPage + ',0 ' + this.widthPage + ',0 0,0'}
        ],
        easing: 'easeOutQuad',
        duration: 1200,
        loop: false
      });
    },
    switchInMenuFromContact(){

      anime({
        targets: '.polymorph',
        points: [
          { value: this.widthPage + ',' + this.heightPage + ' 0,' + this.heightPage + ' 0,0 ' + (this.widthPage / 1.1) + ',0 ' + this.widthPage + ',0'}
        ],
        easing: 'easeOutQuad',
        duration: 1200,
        loop: false
      });
    },
    switchInIndex(){

      document.querySelector(".polymorph").points[0].x = this.widthPage
      document.querySelector(".polymorph").points[0].y = this.heightPage
      document.querySelector(".polymorph").points[1].x = 0
      document.querySelector(".polymorph").points[1].y = this.heightPage
      document.querySelector(".polymorph").points[2].x = 0
      document.querySelector(".polymorph").points[2].y = 0
      document.querySelector(".polymorph").points[3].x = this.widthPage / 4.5
      document.querySelector(".polymorph").points[3].y = 0
      document.querySelector(".polymorph").points[4].x = this.widthPage
      document.querySelector(".polymorph").points[4].y = 0

      anime({
        targets: '.polymorph',
        points: [
          { value: this.widthPage + ',' + this.heightPage + ' 0,' + this.heightPage + ' 0,0 ' + (this.widthPage / 4.5) +',0 ' + (this.widthPage / 3.2) + ',' + (this.heightPage / 1.45)},
          { value: this.widthPage + ',' + this.heightPage + ' 0,' + this.heightPage + ' 0,0 0,0 ' + (this.widthPage / 3.2) + ',' + (this.heightPage / 1.45)}
        ],
        easing: 'easeOutQuad',
        duration: 1200,
        loop: false
      });
    },
    switchInParcours(){

      document.querySelector(".polymorph").points[0].x = this.widthPage
      document.querySelector(".polymorph").points[0].y = this.heightPage
      document.querySelector(".polymorph").points[1].x = 0
      document.querySelector(".polymorph").points[1].y = this.heightPage
      document.querySelector(".polymorph").points[2].x = 0
      document.querySelector(".polymorph").points[2].y = this.heightPage / 4
      document.querySelector(".polymorph").points[3].x = 0
      document.querySelector(".polymorph").points[3].y = 0
      document.querySelector(".polymorph").points[4].x = this.widthPage
      document.querySelector(".polymorph").points[4].y = 0

      // BotRight MidRight BotLeft TopRight TopLeft
      anime({
        targets: '.polymorph',
        points: [
          { value: this.widthPage + ',' + this.heightPage + ' ' + (this.widthPage / 1.35) + ',' + (this.heightPage / 3.5) + ' 0,' + this.heightPage / 4 + ' 0,0 ' + this.widthPage + ',0'},
          { value: this.widthPage + ',' + this.heightPage + ' ' + (this.widthPage / 1.35) + ',' + (this.heightPage / 3.5) + ' 0,' + this.heightPage / 13 + ' 0,0 ' + this.widthPage + ',0'}
        ],
        easing: 'easeOutQuad',
        duration: 1200,
        loop: false
      });
    },
    switchInCompetences(){

      document.querySelector(".polymorph").points[0].x = 0
      document.querySelector(".polymorph").points[0].y = this.heightPage
      document.querySelector(".polymorph").points[1].x = 0
      document.querySelector(".polymorph").points[1].y = this.heightPage
      document.querySelector(".polymorph").points[2].x = this.widthPage
      document.querySelector(".polymorph").points[2].y = this.heightPage
      document.querySelector(".polymorph").points[3].x = this.widthPage
      document.querySelector(".polymorph").points[3].y = 0
      document.querySelector(".polymorph").points[4].x = 0
      document.querySelector(".polymorph").points[4].y = 0

      // BotRight MidRight BotLeft TopRight TopLeft
      anime({
        targets: '.polymorph',
        points: [
          {value: '0,' + this.heightPage + ' ' + (this.widthPage / 10) + ',' + this.heightPage + ' ' + (this.widthPage / 5.2) + ',' + (this.heightPage / 4) + ' ' +  this.widthPage + ',0 ' + this.widthPage + ',0 0,0'},
          {value: '0,' + this.heightPage + ' ' + (this.widthPage / 10) + ',' + this.heightPage + ' ' + (this.widthPage / 6) + ',' + (this.heightPage / 7) + ' ' +  this.widthPage + ',' + (this.heightPage / 4) + ' ' + this.widthPage + ',0 0,0'},
          {value: '0,' + this.heightPage + ' 0,' + this.heightPage + ' ' + (this.widthPage / 6) + ',' + (this.heightPage / 7) + ' ' +  this.widthPage + ',' + (this.heightPage / 4) + ' ' + this.widthPage + ',0 0,0'},
        ],
        easing: 'easeOutQuad',
        duration: 1200,
        loop: false
      });
    },
    switchInContact(){

      document.querySelector(".polymorph").points[0].x = this.widthPage
      document.querySelector(".polymorph").points[0].y = this.heightPage
      document.querySelector(".polymorph").points[1].x = 0
      document.querySelector(".polymorph").points[1].y = this.heightPage
      document.querySelector(".polymorph").points[2].x = 0
      document.querySelector(".polymorph").points[2].y = 0
      document.querySelector(".polymorph").points[3].x = this.widthPage / 1.1
      document.querySelector(".polymorph").points[3].y = 0
      document.querySelector(".polymorph").points[4].x = this.widthPage
      document.querySelector(".polymorph").points[4].y = 0

      anime({
        targets: '.polymorph',
        points: [
          { value: this.widthPage + ',' + this.heightPage + ' 0,' + this.heightPage + ' ' + (this.widthPage / 2) + ',' + (this.heightPage / 1.45) + ' ' + (this.widthPage / 1.2) + ',0 ' + ' ' + this.widthPage + ',0'},
          { value: this.widthPage + ',' + this.heightPage + ' 0,' + this.heightPage + ' ' + (this.widthPage / 2) + ',' + (this.heightPage / 1.45) + ' ' + (this.widthPage / 1.05) + ',0 ' + this.widthPage + ',0'}
        ],
        easing: 'easeOutQuad',
        duration: 1200,
        loop: false
      });
    }
  }
}
</script>

<style scoped>
 .webpage{
    background-color: #f5eded;
    /* background-color: #e6e6e6; */
    /* background-color: white; */
    position: absolute;
    width: 100%;
    overflow: hidden;
  }
  .svgPage{
    /* display: none; */
    /* border: solid black; */
  }
  .polymorph{
    /* fill: #29ABE2; */
    fill: #446491;
    /* fill: #ffab1a; */
  }
</style>
