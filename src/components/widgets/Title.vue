<template>
    <h3 class="title">{{this.text}}</h3>
</template>
<script>
    export default{
        props:{
            text:String
        }
    }
</script>
<style scoped>
    .title {
    text-align: center;
    color: #fff;
    font-family: "Poppins", sans-serif;
    margin-bottom: 2%;
    font-size: 28px;
    font-weight: bold;
    text-shadow: #000 0.5px -0.5px, #000 -0.5px 0.5px, #000 0.5px 0.5px,
            #000 -0.5px -0.5px;
    }
    /*
    .title::before{
        content: "->";
        display: inline;
        color: #ffffff;
        background-color: #2a87bd;
        padding: 0 5px;
        border-radius: 50%;
        margin: 0 10px;
        border: rgb(255, 255, 255) 1px solid;
        text-shadow: #fff 0.5px -0.5px, #fff -0.5px 0.5px, #fff 0.5px 0.5px,
            #fff -0.5px -0.5px;
    }*/
    .title::before{
        content: "</";
        display: inline;
        text-shadow: #000 0.5px -0.5px, #000 -0.5px 0.5px, #000 0.5px 0.5px,
            #000 -0.5px -0.5px;
        color: #38b6ff;
    }
    .title::after{
        content: ">";
        display: inline;
        text-shadow: #000 0.5px -0.5px, #000 -0.5px 0.5px, #000 0.5px 0.5px,
            #000 -0.5px -0.5px;
        color: #38b6ff;
    }
</style>