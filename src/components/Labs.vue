<template>
  <div class="labs" id="labs">
    <Title text="Labs" />
    <div class="cards-contaner">
      <div v-for="project in projects" :key="project.name">
        <CardLabs
          :name="project.name"
          :description="project.description"
          :languages="project.techs"
          :url="project.url"
        />
      </div>
    </div>
  </div>
</template>

<script>
import CardLabs from "./widgets/CardLabs.vue";
import data from "../../public/shared/data.json";
import Title from './widgets/Title.vue';
export default {
    data(){
        return {projects:[]}
    },
    created: function(){
        this.projects = data.projects;
    },
  components: {
    CardLabs,
    Title
  },
};
</script>

<style scoped>
.labs {
  padding: 2%;
  background-color: #07082b;
}
.cards-contaner{
    display: flex;
    flex-wrap:nowrap ;
    overflow-x:auto ;
    flex-direction: row;
    padding: 15px;
    background-color: rgba(0, 0, 0, 0.938);
    border-radius: 15px;
}
.cards-contaner::-webkit-scrollbar{
    height: 10px;
}
.cards-contaner::-webkit-scrollbar-track{
    background-color: #f1f1f1;
    border-radius: 5px;
}
.cards-contaner::-webkit-scrollbar-thumb{
    background-color: #888;
    border-radius: 5px;
}
.cards-contaner::webkit-scrollbar-thumb:hover{
    background-color: #555;
}
</style>
