<template>
    <div class="card-labs">
        <p class="project-name">{{this.name}}</p>
        <p class="project-description">{{this.description}}</p>
        <div class="techs-container">
            <div v-for="lang in languages" :key="lang.name">
                <img :src=lang.svg :alt=lang.name class="tech-image" draggable="false">
            </div>
        </div>
        <a class="link" target="_blank" :href=this.url> <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M12 2c5.514 0 10 4.486 10 10s-4.486 10-10 10-10-4.486-10-10 4.486-10 10-10zm0-2c-6.627 0-12 5.373-12 12s5.373 12 12 12 12-5.373 12-12-5.373-12-12-12zm0 6c-3.313 0-6 2.686-6 6 0 2.651 1.719 4.9 4.104 5.693.3.056.396-.13.396-.289v-1.117c-1.669.363-2.017-.707-2.017-.707-.272-.693-.666-.878-.666-.878-.544-.373.041-.365.041-.365.603.042.92.619.92.619.535.917 1.403.652 1.746.499.054-.388.209-.652.381-.802-1.333-.152-2.733-.667-2.733-2.965 0-.655.234-1.19.618-1.61-.062-.153-.268-.764.058-1.59 0 0 .504-.161 1.65.615.479-.133.992-.199 1.502-.202.51.002 1.023.069 1.503.202 1.146-.776 1.648-.615 1.648-.615.327.826.121 1.437.06 1.588.385.42.617.955.617 1.61 0 2.305-1.404 2.812-2.74 2.96.216.186.412.551.412 1.111v1.646c0 .16.096.347.4.288 2.383-.793 4.1-3.041 4.1-5.691 0-3.314-2.687-6-6-6z"/></svg></a>

    </div>
</template>
<script>
    export default{
        props:{
            name:String,
            url:String,
            description:String,
            languages:[]
        }
    }
</script>

<style scoped>
a>svg{
    fill: rgb(245, 245, 245);
    transition: 300ms;
}
a>svg:hover{
    opacity: 0.8;
}
    .project-name{
        font-family: 'Anonymous Pro', monospace;
        color: rgb(233, 233, 233);
        margin-top: 10px;
        font-size: 22px;
    }
    .project-description{
        color: rgb(216, 216, 216);
        font-family: 'Nunito', sans-serif;
        text-shadow: 1px 1px #000;
        
        padding: 2px 10px;
        font-size: 18px;
        box-sizing: border-box;
        margin-top:15px ;
}

    
    .tech-image{
        width: 50px;
    }
    .card-labs{
        width: 300px;
        height: 350px;
        background-color: #040411;
        border-radius: 10px;
        padding: 2%;
        margin: 10px;
        display: flex;
        flex-direction: column;
        align-content: center;
        justify-content: center;
        align-items: center;
        animation: neonColor 4500ms  ease alternate-reverse infinite ;
    }
    /*
        border: rgb(22, 22, 22) 2px solid; */
    @keyframes neonColor {
        0%{
            border: #516d7e 2px solid;
            text-shadow: 1px 1px #000;
        }
        33%{

            border: #38B6FF 2px solid;
            box-shadow: -1px -1px 0 #38B6FF, 1px -1px 0 #38B6FF, -1px 1px 0 #38B6FF, 1px 1px 0 #38B6FF, 0 -2px 4px, 0 0 2px, 0 0 3px #38B6FF, 0 0 7px #38B6FF, 0 0 1px #38B6FF, 0 1px 2px #000;
        }
        50%{
            border: #516d7e 2px solid;
            box-shadow: 1px 1px #000;
        }
        100%{
            border: #38B6FF 2px solid;
            box-shadow: -1px -1px 0 #38B6FF, 1px -1px 0 #38B6FF, -1px 1px 0 #38B6FF, 1px 1px 0 #38B6FF, 0 -2px 4px, 0 0 2px, 0 0 3px #38B6FF, 0 0 7px #38B6FF, 0 0 1px #38B6FF, 0 1px 2px #000;
        }

    }
    .techs-container{
        display: flex;
        flex-direction: row;
        flex-wrap: nowrap;
        margin: 15px 0;
    }
    .link{
        width: 55px;
        height: 55px;
        display: flex;
        flex-direction: column;
        justify-content: center;
    }
</style>