<template>
  <div  class="skills" id="skills">
    <Title text="Skills" />

    <div class="languages-container">
      <div v-for="lang in languages" :key="lang.name">
        <Lang :name="lang.name" :url="lang.svg" />
      </div>
    </div>
  </div>
</template>

<script>
import data from "../../public/shared/data.json";
import Lang from "./widgets/CardSkills.vue";
import Title from './widgets/Title.vue';

export default {
  data() {
    return { languages: {} };
  },
  created: function() {
    this.languages = data.languages;
  },
  components: {
    Lang,
    Title
  },
};
</script>

<style scoped>

.skills {
  background-color: #181b69;
  padding: 2% 2% 2% 2%;
}
.languages-container {
  flex-direction: row;
  display: flex;
  width: 90vw;
  flex-wrap: nowrap;
  overflow-y: hidden;
  overflow-x: visible;
  padding: 15px;
  background-color: rgba(0, 0, 0, 0.938);
  border-radius: 15px;
}

.languages-container::-webkit-scrollbar{
    height: 10px;
}
.languages-container::-webkit-scrollbar-track{
    background-color: #f1f1f1;
    border-radius: 5px;
}
.languages-container::-webkit-scrollbar-thumb{
    background-color: #888;
    border-radius: 5px;
}
.languages-container::webkit-scrollbar-thumb:hover{
    background-color: #555;
}



</style>
