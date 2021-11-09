<template>
  <div  class="skills" id="skills">
    <div class="title-toggle">
      <Title text="Skills" />
      <div class="toggle-container">
        <svg xmlns="http://www.w3.org/2000/svg" class="icon" focusable="false" viewBox="0 0 12 12">
            <g>
              <rect class="rect" width="2" height="5" x="2" y="4"/>
              <rect class="rect" width="2" height="5" x="5" y="4" />
              <rect class="rect" width="2" height="5" x="8" y="4"/>
            </g>
          </svg>
        
            <div class="skill-button-container" @click="toggleSkillsList()">
                  <div class="skill-button" id="skill-button">
                  </div>
            </div>
            <svg xmlns="http://www.w3.org/2000/svg" class="icon" focusable="false" viewBox="0 0 12 12">
            <g>
              <rect class="rect" width="2" height="2" x="2" y="2" rx=".5" ry=".5"/>
              <rect class="rect" width="2" height="2" x="5" y="2" rx=".5" ry=".5"/>
              <rect class="rect" width="2" height="2" x="8" y="2" rx=".5" ry=".5"/>
              <rect class="rect" width="2" height="2" x="8" y="5" rx=".5" ry=".5"/>
              <rect class="rect" width="2" height="2" x="5" y="5" rx=".5" ry=".5"/>
              <rect class="rect" width="2" height="2" x="2" y="5" rx=".5" ry=".5"/>
              <rect class="rect" width="2" height="2" x="2" y="8" rx=".5" ry=".5"/>
              <rect class="rect" width="2" height="2" x="5" y="8" rx=".5" ry=".5"/>
              <rect class="rect" width="2" height="2" x="8" y="8" rx=".5" ry=".5"/>
            </g>
          </svg>
          </div>
      </div>
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
    return { languages: {}, isGrid:false };
  },
  created: function() {
    this.languages = data.languages;
  },
  components: {
    Lang,
    Title
  },
  methods:{
    toggleSkillsList(){
      this.isGrid=!this.isGrid;
      this.loadList();
    },
    loadList(){
        const a = document.getElementById("skill-button");
        if(this.isGrid){
          a.style.marginLeft  = a.parentElement.offsetWidth - a.offsetWidth - 
          parseInt(window.getComputedStyle(a.parentElement, null).getPropertyValue('padding-right').split("px")[0])* 2 
          + "px"
          this.turnIntoGrid();
          /* console.log(document.querySelector(".skill-button-container>.skill-button)) */
        }else{
          a.style.marginLeft  = 0 + "px"
          this.turnIntoList();
        } 
    },
    turnIntoList(){
        this.nulifyStyle();
        const element = document.getElementsByClassName("languages-container")[0];
        element.style.display = "flex";
        element.style.flexWrap = "nowrap";
        element.style.overflowX = "auto";
        element.style.flexDirection = "row";

        element.style.width = "auto";
      },
      turnIntoGrid(){
        this.nulifyStyle();
        const element = document.getElementsByClassName("languages-container")[0];
         element.style.display = "grid";
         element.style.gridGap = "15px";
         element.style.gridTemplateColumns = "repeat(auto-fill, minmax(220px,auto))";
        element.style.width = "auto";
      },
      nulifyStyle(){
        const element = document.getElementsByClassName("languages-container")[0];
        element.style.display = "none";
        element.style.flexWrap = "none";
        element.style.overflowX = "none";
        element.style.flexDirection = "none";
        element.style.width = "none";
        element.style.display = "none";
         element.style.gridGap = "none";
         element.style.gridTemplateColumns = "none";
      }

  }
};
</script>

<style scoped>

.skills {
  background-color: #181b69;
  padding: 10px 0 10px 3% ;
  
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

  justify-items: center;
}
.icon{
  width: 48px;
  fill: #f1f1f1;
}
.title-toggle{
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  align-content: center;
  margin: 10px 0;
}
.skill-button-container{
  width: 95px;
  background-color: rgba(250, 250, 250, 0.8);
  cursor: pointer;
  border-radius: 10px;
  padding: 2px;
}
.toggle-container{
  display: flex;
  flex-direction: row;
  margin-left: 2vw;
}
.skill-button{
  border-radius: 10px;
  width: 50px;
  height: 100%;
  transition: 350ms;
  animation-timing-function: cubic-bezier(0.78,-0.44, 0.23, 1.43);
  background-color: #044c75;
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
/* */
@media (max-width: 600px){
  .skills{
  padding: 15px 4px 30px;
  }
}

</style>
