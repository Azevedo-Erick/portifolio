<template>
    <div class="card-skill">
        <img :src="this.url" class="lang-svg" draggable="false"/>
        <p class="lang-name">{{this.name}}</p>
    </div>
</template>

<script>
    export default{
        props:{
            name:String,
            url:String
        },
    }
</script>

<style scoped>
    .card-skill{
        display: flex;
        flex-direction: column;
        height: 200px;
        width: 180px;
        background-image: linear-gradient(to bottom, rgba(8, 4, 24, 0.85) 95%, #150058 5%);
        border: 2px #020202 solid;
        border-radius: 10px;
        padding: 15px;
        align-items: center;
        margin: 10px;
    }
    .lang-svg{
        width: 150px;
        height: 150px;
    }
    .lang-name{
        font-family: 'GlacialIndifferenceRegular';
        color: #fff;
        margin-top: 10px;
        font-size: 22px;
    }
</style>