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
    <div class="container-cards">
      <card-language
        class="card"
        v-for="card in listCards"
        :key="card.title"
        :title="card.title"
        :imgUrl="card.imgUrl"
        :wikipedia="card.wikipedia"
        :description="card.description"
      ></card-language>
    </div>
  </div>
</template>

<script>
import CardLanguage from "../CardLanguage.vue";

export default {
  name: "ContactPage",
  components: {
    CardLanguage,
  },
  data: function () {
    return {
      listCards: [
        {
          title: "HTML",
          imgUrl: "https://www.w3.org/html/logo/downloads/HTML5_Logo_512.png",
          description:
            "HTML est un langage de balise qui permet de créer et de représenter le contenu et la structure d'une page web.",
          wikipedia: "https://fr.wikipedia.org/wiki/HTML5",
        },
        {
          title: "CSS",
          imgUrl:
            "https://upload.wikimedia.org/wikipedia/commons/thumb/d/d5/CSS3_logo_and_wordmark.svg/1200px-CSS3_logo_and_wordmark.svg.png",
          description:
            "CSS est un langage informatique qui permet de gérer le design d'une page web.",
          wikipedia:
            "https://fr.wikipedia.org/wiki/Feuilles_de_style_en_cascade",
        },
        {
          title: "JavaScript",
          imgUrl:
            "https://upload.wikimedia.org/wikipedia/commons/thumb/b/b6/Badge_js-strict.svg/555px-Badge_js-strict.svg.png",
          description:
            "JavaScript est un langage de script qui va permettre d'intéragir avec l'internaute depuis une page web.",
          wikipedia: "https://fr.wikipedia.org/wiki/JavaScript",
        },
        {
          title: "Bootstrap",
          imgUrl:
            "https://sdtimes.com/wp-content/uploads/2018/01/bootstrap-stack.png",
          description:
            "Bootstrap est un framework qui permet de concevoir plus rapidement un design responsive d'une page web.",
          wikipedia: "https://fr.wikipedia.org/wiki/Bootstrap_(framework)",
        },
        {
          title: "Node.js",
          imgUrl:
            "https://upload.wikimedia.org/wikipedia/commons/thumb/d/d9/Node.js_logo.svg/1200px-Node.js_logo.svg.png",
          description:
            "Node.js est un framework qui permet de gérer le coté serveur d'une page web avec JavaScript.",
          wikipedia: "https://fr.wikipedia.org/wiki/Node.js",
        },
        {
          title: "Vue.js",
          imgUrl:
            "https://upload.wikimedia.org/wikipedia/commons/thumb/9/95/Vue.js_Logo_2.svg/1200px-Vue.js_Logo_2.svg.png",
          description:
            "Vue est un framework qui permet de programmer l'interface visuel d’un site web.",
          wikipedia: "https://fr.wikipedia.org/wiki/Vue.js",
        },
        {
          title: "React.js",
          imgUrl:
            "https://upload.wikimedia.org/wikipedia/commons/thumb/a/a7/React-icon.svg/1200px-React-icon.svg.png",
          description:
            "Vue est un framework qui permet de programmer l'interface visuel d’un site web.",

          wikipedia: "https://fr.wikipedia.org/wiki/React_(JavaScript)",
        },
        {
          title: "PHP",
          imgUrl:
            "https://upload.wikimedia.org/wikipedia/commons/thumb/2/27/PHP-logo.svg/1280px-PHP-logo.svg.png",
          description:
            "PHP est un langage de programmation pour développer le coté serveur d'une page web.",
          wikipedia: "https://fr.wikipedia.org/wiki/PHP",
        },
        {
          title: "Symfony",
          imgUrl:
            "https://cdn.freebiesupply.com/logos/thumbs/2x/symfony-logo.png",
          description:
            "Symfony est un framework qui permet d'accélerer le développement d'un site ou d'une application web à l'aide de PHP.",
          wikipedia: "https://fr.wikipedia.org/wiki/Symfony",
        },
        {
          title: "Wordpress",
          imgUrl:
            "https://upload.wikimedia.org/wikipedia/commons/thumb/9/98/WordPress_blue_logo.svg/1200px-WordPress_blue_logo.svg.png",
          description:
            "Wordpress est un logiciel de système de gestion de contenu qui permet de créer des sites internets complets.",
          wikipedia: "https://fr.wikipedia.org/wiki/WordPress",
        },
        {
          title: "Docker",
          imgUrl:
            "https://mountainss.files.wordpress.com/2017/01/docker-logo.png",
          description:
            "Docker est un logiciel qui permet de concevoir, tester et développer rapidement des applications dans des conteneurs logiciel.",
          wikipedia: "https://fr.wikipedia.org/wiki/Docker_%28logiciel%29",
        },
        {
          title: "Java",
          imgUrl:
            "https://www.softexia.com/wp-content/uploads/2017/04/Java-logo.png",
          description:
            "Java est un langage de programmation orienté objet, il est polyvalent et permet de créer des applications complètes sur n'importe quel système.",

          wikipedia: "https://fr.wikipedia.org/wiki/Java_(technique)",
        },
        {
          title: "Python",
          imgUrl:
            "https://upload.wikimedia.org/wikipedia/commons/thumb/c/c3/Python-logo-notext.svg/1200px-Python-logo-notext.svg.png",
          description:
            "Python est un langage de programmation orienté objet, il est polyvalent et très utilisés dans le BigData, le calcul numérique et les scripts.",
          wikipedia: "https://fr.wikipedia.org/wiki/Python_%28langage%29",
        },
        {
          title: "Android Studio",
          imgUrl:
            "https://appjoy.org/wp-content/uploads/2016/05/Android-Studio-Logo.png",
          description:
            "Android Studio est un logiciel qui permet de développer des application android.",
          wikipedia: "https://fr.wikipedia.org/wiki/Android_Studio",
        },
        {
          title: "PL/SQL",
          imgUrl: "https://metamug.com/article/images/pl-sql-database.jpg",
          description:
            "PL/SQL est un langage de programmation qui permet de manipuler des bases de données.",
          wikipedia: "https://fr.wikipedia.org/wiki/PL/SQL",
        },
        {
          title: "C#",
          imgUrl:
            "https://www.onlinebooksreview.com/uploads/blog_images/2018/01/27_c-sharp-logo-filled.png",
          description:
            "C# est un langage de programmation orienté objet, il est robuste et sécurisé et permet de créer des applications complètes.",
          wikipedia: "https://fr.wikipedia.org/wiki/C_sharp",
        },
        {
          title: "Bash",
          imgUrl:
            "https://raw.githubusercontent.com/odb/official-bash-logo/master/assets/Logos/Icons/PNG/512x512.png",
          description:
            "Bash est un langage script qui permet d'interpréter et d'utiliser des commandes Linux.",
          wikipedia: "https://fr.wikipedia.org/wiki/Bourne-Again_shell",
        },
        {
          title: "Git",
          imgUrl:
            "https://git-scm.com/images/logos/downloads/Git-Icon-Black.png",
          description:
            "Git est un logiciel de gestions de versions libre qui permet à plusieurs personnes de programmer sur le même projet en même temps.",
          wikipedia: "https://fr.wikipedia.org/wiki/Git",
        },
      ],
    };
  },
  methods: {
    switchInMenu() {
      this.$emit("back");
    },
  },
};
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
}

.competencesPage {
  display: flex;
  flex-direction: column;
  align-items: center;
  /* border: solid black; */
}
header {
  display: flex;
  justify-content: flex-end;
  align-items: center;
  width: 100%;
  height: 30vh;
}
header .btnMenu {
  z-index: 3;
  width: 50px;
  background-size: cover;
  margin-right: 5vw;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.barre-hamburger {
  width: 100%;
  border-top: 4px solid black;
  margin-top: 15px;
}
header .btnMenu:hover > .barre-hamburger {
  animation-name: animationHamburger;
  animation-duration: 0.7s;
  animation-timing-function: ease;
  margin-top: 10px;
  width: 66%;
}
.title {
  /* margin-top: 2vh; */
  margin-left: 5vw;
  font-size: 30px;
  z-index: 3;
}
.container-cards {
  margin-top: 5vh;
  margin-left: 5vw;
  width: 70%;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

@keyframes animationHamburger {
  0% {
    margin-top: 15px;
    width: 100%;
  }
  100% {
    margin-top: 10px;
    width: 66%;
  }
}

@keyframes animationHamburgerSmall {
  0% {
    margin-top: 7px;
    width: 100%;
  }
  100% {
    margin-top: 5px;
    width: 66%;
  }
}

@media (max-width: 680px) {
  header {
    height: 20vh;
  }
  h1 {
    font-size: 30px;
    margin-top: 5vh;
  }
  header .btnMenu {
    width: 30px;
  }
  .barre-hamburger {
    border-top: 2px solid black;
    margin-top: 7px;
  }
  header .btnMenu:hover > .barre-hamburger {
    animation-name: animationHamburgerSmall;
    margin-top: 5px;
    width: 66%;
  }
}

@media (min-width: 681px) and (max-width: 1279px) {
  h1 {
    font-size: 40px;
  }
}

@media (min-width: 1280px) {
  h1 {
    font-size: 50px;
  }
}
</style>