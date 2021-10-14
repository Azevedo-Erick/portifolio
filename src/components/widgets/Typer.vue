<template>
    <div>
        <p id="typer" @click="type()" class="char">AAA</p>
    </div>
</template>
<script>

    
    export default{
        props:{ 
            text: String
        },
        init(){
            this.text = this.props.text
        },
        methods:{
            type(){
                const textHandler = document.getElementById("typer");
                const data = this.text.split(",");
                textHandler.innerHTML = "";
                let timeIndex = 1;
                
                for(let i = 0; i<data.length; i++){
                    for(let j = 0; j<data[i].length; j++, timeIndex++){
                        setTimeout(()=>{
                            textHandler.innerHTML += data[i][j];
                            if(" "===data[i][j] && data[i][j-1] != "r" && data[i][j-2] != "o"){
                                textHandler.innerHTML = "";
                            }
                        },300*timeIndex)
                        

                    }
                   
                }
                
            
            }
        }
    }
</script>
<style scoped>
.vue-typer {
  
}
.char {
  color: #38b6ff;
  margin: 45px 0 5px 0;
  font-size: 28px;
  font-family: "Anonymous Pro", monospace;
}

.char::after {
    content: "";
    padding: 2px;
    background-color: blue;
  font-weight: bold;
  width: 2px;
  animation: esmaecer 2000ms ease-in-out  infinite alternate-reverse;
}
@keyframes esmaecer{
    0%,100%{
        opacity: 0%;
    }
    50%{
        opacity: 100%;
    }
}
</style>