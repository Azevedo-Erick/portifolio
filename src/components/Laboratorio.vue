<template>
  <div class="laboratorio" id="laboratorio">
    <div class="title-toggle">
      <Title text="Laboratório" />
      <div class="toggle-container">
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
        
          <div class="button-container" @click="toggleList()">
                <div class="button" id="button">
                </div>
          </div>
           <svg xmlns="http://www.w3.org/2000/svg" class="icon" focusable="false" viewBox="0 0 12 12">
          <g>
            <rect class="rect" width="2" height="5" x="2" y="4"/>
            <rect class="rect" width="2" height="5" x="5" y="4" />
            <rect class="rect" width="2" height="5" x="8" y="4"/>
          </g>
        </svg>
        
      </div>
    </div>
    <div class="cards-contaner">
      <div v-for="project in projects" :key="project.name">
        <CardLaboratorio
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
import CardLaboratorio from "./widgets/CardLaboratorio.vue";
import data from "../../public/shared/data.json";
import Title from './widgets/Title.vue';
export default {
    data(){
        return {projects:[], isList:false}
    },
    created: function(){
        this.projects = data.projects;
    },
    mounted(){
      this.loadList();
    },
    methods:{
      toggleList(){
        this.isList = !this.isList;
        this.loadList();
      },
      loadList(){
         const a = document.getElementById("button");
        if(this.isList){
          a.style.marginLeft  = a.parentElement.offsetWidth - a.offsetWidth - 
          parseInt(window.getComputedStyle(a.parentElement, null).getPropertyValue('padding-right').split("px")[0])* 2 
          + "px"
          this.turnIntoList();
        }else{
           a.style.marginLeft  = 0 + "px"
           this.turnIntoGrid();
        } 
      },
      turnIntoList(){
        this.nulifyStyle();
        const element = document.getElementsByClassName("cards-contaner")[0];
        element.style.display = "flex";
        element.style.flexWrap = "nowrap";
        element.style.overflowX = "auto";
        element.style.flexDirection = "row";

        element.style.width = "auto";
      },
      turnIntoGrid(){
        this.nulifyStyle();
        const element = document.getElementsByClassName("cards-contaner")[0];
         element.style.display = "grid";
         element.style.gridGap = "15px";
         element.style.gridTemplateColumns = `repeat(auto-fill, minmax(300px,auto))`;
        element.style.width = "auto";
      },
      nulifyStyle(){
        const element = document.getElementsByClassName("cards-contaner")[0];
        element.style.display = "none";
        element.style.flexWrap = "none";
        element.style.overflowX = "none";
        element.style.flexDirection = "none";
        element.style.width = "none";
        element.style.display = "none";
         element.style.gridGap = "none";
         element.style.gridTemplateColumns = "none";
      }
    },
  components: {
    CardLaboratorio,
    Title,
  },
};
</script>

<style scoped>
.laboratorio {
  background-color: #07082b;
  padding: 15px 15px 30px;
}

.cards-contaner{
  justify-items: center;
    width: auto;
    padding: 15px; 
    background-color: #000000ef;
    border-radius: 15px;
    
  align-content: center;
  align-items: center;
}
.toggle-container{
  display: flex;
  flex-direction: row;
  margin-left: 2vw;
}
.title-toggle{
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  align-content: center;
  margin: 10px 0;
}
.icon{
  width: 48px;
  fill: #f1f1f1;
}
.cards-contaner>div{
  width: min-content;
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

.button-container{
  width: 95px;
  background-color: rgba(250, 250, 250, 0.8);
  cursor: pointer;
  border-radius: 10px;
  padding: 2px;
}
.button{
  border-radius: 10px;
  width: 50px;
  height: 100%;
  transition: 350ms;
  animation-timing-function: cubic-bezier(0.78,-0.44, 0.23, 1.43);
  background-color: #044c75;
}
@media (max-width: 600px) {
  .title-toggle{
    flex-direction: column;
  }
  .toggle-container{
    margin: 10px 0;
  }
}
/*padding: 15px 4px 30px;*/
</style>
