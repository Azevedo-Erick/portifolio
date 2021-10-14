<template>
    <nav>
        <div class="name-container">
            <i class="color-tag">&lt;/</i>
            <p>Azevedo-Erick</p>
            <i class="color-tag">&gt;</i>
        </div>
        <div class="mobile-menu" @click="mobileMenu()">
            <div class="line1" ></div>
            <div class="line2"></div>
            <div class="line3"></div>
        </div>
        <div class="navegation" id="nav">
            <a @click="scrollTo('about')">About</a>
            <a @click="scrollTo('skills')">Skills</a>
            <a @click="scrollTo('labs')">Labs</a>
            <a @click="scrollTo('contact')">Contact</a>
        </div>
    </nav>
</template>

<script>
       export default {
        data(){
            return{
                active:false,
                scrollValue:window.scrollY,
            }
        }
        ,
        methods:{
            scrollTo(elName){
                let element = document.getElementById(elName);
                element.scrollIntoView({behavior:'smooth'});
                if(this.active){
                    this.toggleActive();
                    }
                
            },
            
            mobileMenu(){
               
                this.toggleActive();
                if(document.getElementsByTagName("html")[0].clientWidth > 1000){   
                        document.getElementById("nav").style.transform = "translateX(100%)";
                }
            },
            toggleActive(){
                 document.getElementById("nav").children.forEach(element=>{element.style.display="flex"})
                
                this.active = !this.active
                if(this.active){
                    document.getElementById("nav").style.transform = "translateX(0)";
                    document.getElementsByTagName("html")[0].style.overflowY = "hidden";
                    document.getElementById("nav").style.display = "flex";
                    
                    this.animateLinks();
                    console.log("if")
                    }else{
                        console.log("else")
                        document.getElementsByTagName("html")[0].style.overflowY = "scroll"
                        document.getElementById("nav").style.display = "none";
                        document.getElementById("nav").style.transform = "translateX(100%)";
                        
                        
                }
                
            },
            animateLinks(){
                document.querySelectorAll("#nav > a").forEach((link, i)=>{
                   link.style.animation? console.log("a"): console.log(link);
                    if(link.style.animation){
                        link.style.animation = " "
                    }else{ 
                        link.style.animation = `navLinkFade 500ms easein forwards ${i/7*300}ms`;
                        
                        }
                    
                })
            },
            navPercentage(){
                let element = document.getElementsByTagName("nav");
                if(this.scrollValue>=65){
                    element.style.position = "fixed"
                    element.style.height = "30px"
                    console.log(this.scrollValue);
                }else{
                    element.style.position = "unset"
                    element.style.height = ""
                    console.log(this.scrollValue);
                }
            }
        }
    }
</script>
<style scoped>
@media screen and (max-width:600) {
        .name-container{
            display: none;
        }
    }
    nav{
        background-color: #07082b;
        display: flex;
        flex-wrap: nowrap;
        flex-direction: row;
        padding: 1% 4% 1% 2%;
        justify-content: space-between;
         height: calc(4vh - 1vw);
        width: 94%;
        align-items: center;
    }
    .navegation{
        display: flex;
        justify-content: flex-end;
    }
    .navegation > a{
        font-family: 'Bebas Neue';
        font-size: 32px;
        color: #fff;
        margin-right: 10px;
        cursor: pointer;
        padding: 2px 4px;
        transition: 300ms;
    }
    .navegation > a:hover{
        opacity: 0.6;
    }
    .name-container{
        font-family: 'GlacialIndifferenceRegular';
        font-size: 32px;
        color: #fff;
        display: flex;
        flex-direction: row;
    }
    .color-tag{
        animation: neonColor 2500ms cubic-bezier(0.22, 0.07, 0.56, 0.68)  alternate-reverse infinite ;
    }
    @keyframes neonColor {
        0%{
            color: #516d7e;
            text-shadow: 1px 1px #000;
        }
        33%{

            color: #38B6FF;
            text-shadow: -1px -1px 0 #38B6FF, 1px -1px 0 #38B6FF, -1px 1px 0 #38B6FF, 1px 1px 0 #38B6FF, 0 -2px 4px, 0 0 2px, 0 0 3px #38B6FF, 0 0 7px #38B6FF, 0 0 1px #38B6FF, 0 1px 2px #000;
        }
        50%{
            color: #516d7e;
            text-shadow: 1px 1px #000;
        }
        100%{
            color: #38B6FF;
            text-shadow: -1px -1px 0 #38B6FF, 1px -1px 0 #38B6FF, -1px 1px 0 #38B6FF, 1px 1px 0 #38B6FF, 0 -2px 4px, 0 0 2px, 0 0 3px #38B6FF, 0 0 7px #38B6FF, 0 0 1px #38B6FF, 0 1px 2px #000;
        }

    }
    .mobile-menu div{
        width: 32px;
        height: 2px;
        background-color: #fff;
        margin: 8px;
    }
    .mobile-menu{
        cursor: pointer ;
        display: none;
    }
    @media (max-width: 1000px) {
        nav{

            position: fixed;
            z-index: 2;
            width: 98vw;
            height: 3vh;
        }
        .navegation{
            position: fixed;
            top:4vh;
            right: 0;
            z-index: 2;
            width: 100%;
            height: 98vh;
            background-color: #07082b;
            flex-direction: column;
            align-content: center;
            align-items: center;
            justify-content: space-evenly;
            transform: translateX(100%);
            transition: transform 300ms ease-in-out;
        }
        .navegation.active{
            transform: translateX(0);
        }
        .mobile-menu{
            display: block;
        }
        .navegation > a{
            font-family: 'Bebas Neue';
            font-size: 32px;
            color: #fff;
            margin-right: 10px;
            padding: 10% 100vw;
            display: none;
        }

    }
    @keyframes navLinkFade {
        from{
            opacity: 0;
            transform: translateX(50px);
        }
        to{
            opacity: 1;
            transform: translateX(0);
        }
    }
</style>