<template>
  <li class="cardcontainer">
    <div class="thecard">
      <div class="thefront">
        <!-- <div class="img-card" :style="{backgroundImage:`url(${imgUrl})`}"></div> -->
        <img class="img-card" :src="imgUrl" alt="card competence" />
        <h1>{{ title }}</h1>
      </div>

      <div class="theback">
        <p>{{ description }}</p>
        <a :href="wikipedia" target="_blank">Wikipedia</a>
      </div>
    </div>
  </li>
</template>

<script>
export default {
  name: "CardLanguage",
  props: {
    title: {
      type: String,
      default: "",
    },
    imgUrl: {
      type: String,
      default: "",
    },
    wikipedia: {
      type: String,
      default: "",
    },
    description: {
      type: String,
      default: "",
    },
  },
  created() {
    // console.log(this.imgUrl)
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
li {
  list-style: none;
  margin: 1vw;
}
.thecard {
  position: relative;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border-radius: 10px;
  overflow: hidden;
}
.thefront {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border-radius: 10px;
  backface-visibility: hidden;
  overflow: hidden;
  /* background-color: #29ABE2; */
  background-color: #ffab1a;
  color: white;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-end;
}
.theback {
  position: absolute;
  top: 100%;
  left: 0;
  width: 100%;
  height: 100%;
  border-radius: 10px;
  overflow: hidden;
  /* background: #1885b4; */
  background-color: #ff5f1a;
  color: #fff;
  text-align: center;
}
.thecard:hover > .theback {
  animation-name: hoverCard;
  animation-timing-function: ease;
  animation-duration: 1s;
}
.theback:hover {
  top: 0%;
}
.theback a {
  color: white;
}
.thefront h1 {
  font-family: "Helvetica", sans-serif;
  font-weight: bold;
  font-size: 20px;
  margin: 10px 0;
  text-align: center;
}
.theback p {
  font-family: "Helvetica", sans-serif;
  padding: 15px;
  font-weight: normal;
  font-size: 13px;
}
@keyframes hoverCard {
  0% {
    top: 100%;
  }

  100% {
    top: 0%;
  }
}

@media (max-width: 680px) {
  .cardcontainer {
    width: 90px;
    height: 130px;
    background: none;
  }
  .img-card {
    height: 70px;
    width: 70px;
    object-fit: contain;
  }
  .thefront h1 {
    font-size: 12px;
    margin: 10px 0;
  }
  .theback {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .theback p {
    display: none;
  }
  .theback a {
    font-size: 12px;
  }
}

@media (min-width: 681px) and (max-width: 1279px) {
  .cardcontainer {
    width: 180px;
    height: 205px;
    background: none;
  }
  .img-card {
    height: 140px;
    width: 140px;
    object-fit: contain;
  }
  .thefront h1 {
    font-size: 18px;
    margin: 10px 0;
  }
}

@media (min-width: 1280px) {
  .cardcontainer {
    width: 200px;
    height: 220px;
    background: none;
  }
  .img-card {
    height: 150px;
    width: 150px;
    object-fit: contain;
  }
  .thefront h1 {
    font-size: 20px;
    margin: 10px 0;
  }
}
</style>
