<template>
  <div class="container">
    <vue-typer
    class="tp"
      :text="[
        'Desenvolvedor Nodejs',
        'Desenvolvedor Vuejs',
        'Desenvolvedor Flutter',
        'Desenvolvedor Java',
        '',
      ]"
      :repeat="Infinity"
      :shuffle="true"
      initial-action="typing"
      :pre-type-delay="70"
      :type-delay="70"
      :pre-erase-delay="2000"
      :erase-delay="260"
      erase-style="select-all"
      :erase-on-complete="true"
      caret-animation="expand"
    ></vue-typer>
    <p class="name-presentation">Erick Azevedo Sousa</p>
    <p class="description">
      Apenas um estudante de Sistemas de Informação, interessado pelo
      desenvolvimento web , focado em mobile com Flutter e apaixonado por games.
    </p>
    <button class="download-cv" onClick="console.log('hello')">
      Download CV
    </button>
    <div class="particles">
      <vue-particles
        color="#dedede"
        :particleOpacity="0.9"
        :particlesNumber="90"
        shapeType="polygon"
        :particleSize="2"
        linesColor="#dedede"
        :linesWidth="0.4"
        :lineLinked="true"
        :lineOpacity="0.9"
        :linesDistance="150"
        :moveSpeed="5"
        :hoverEffect="true"
        hoverMode="grab"
        :clickEffect="false"
        clickMode="push"
      >
      </vue-particles>
    </div>
  </div>
</template>

<script>
import { VueTyper } from "vue-typer";

export default {
  components: {
    VueTyper
  },
};
</script>

<style scooped>
.particles {
  left: 25%;
  top: 5%;
  position: absolute;
  width: 75%;
  height: 76%;
}
.container {
  background-image: linear-gradient(to right bottom, #040b2d 1%, #0e1344);
  background-repeat: no-repeat;
  height: 400px;
  display: flex;
  flex-direction: column;
  padding: 1% 3%;
  position: relative;
}
.name-presentation {
  font-family: "Anton", sans-serif;
  color: #fff;
  font-size: 20px;
  text-shadow: 1px 1px#000000;
  margin-bottom: 10px;
}
.description {
  font-family: "GlacialIndifferenceRegular";
  color: #fff;
  width: 315px;
  font-size: 22px;
  margin-bottom: 10px;
  text-align: start;
  text-shadow: 1.1px 1.1px#000000;
}
.vue-typer {
  margin: 45px 0 5px 0;
  font-size: 28px;
  font-family: "Anonymous Pro", monospace;
}
.custom.char {
  color: #38b6ff;
  text-shadow: 1.5px 1.5px#000000;
  }
.custom.char.selected,
.custom.caret {
  box-shadow: #000000 1.5px 1.5px;
  background-color: #264f78;
}
.custom.caret {
  font-weight: bold;
  width: 2px;
}
.download-cv {
  font-family: "Bebas Neue";
  color: rgb(218, 218, 218);
  border: 3px solid #38b6ff;
  border-radius: 10px;
  padding: 25px;
  width: 145px;
  font-size: 28px;
  text-shadow: 1.5px 1.5px#000000;
  box-shadow: #000000 1.5px 1.5px;
  text-align: center;
  margin-left: 30px;
  transition: 1000ms;
  background-color: rgba(180, 184, 202, 0);
  cursor: pointer;
}
.download-cv:hover {
  border: rgb(196, 196, 196) 3px solid;
}
</style>
