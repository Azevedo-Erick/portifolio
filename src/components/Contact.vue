<template>
  <div class="contact" id="contact">
    <div class="container-contact">
      <div class="social-handler">
          <!--Linkedin-->
          <a
            href="https://www.linkedin.com/in/erick-azevedo-sousa-0589881b1/"
            target="_blank"
          >
            <svg
              class="icon"
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 24 24"
            >
              <path
                d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"
              />
            </svg>
          </a >
          <!--Github-->
          <a  href="https://github.com/Azevedo-Erick"
            target="_blank">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="icon"
              viewBox="0 0 24 24"
            >
              <path
                d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-4.466 19.59c-.405.078-.534-.171-.534-.384v-2.195c0-.747-.262-1.233-.55-1.481 1.782-.198 3.654-.875 3.654-3.947 0-.874-.312-1.588-.823-2.147.082-.202.356-1.016-.079-2.117 0 0-.671-.215-2.198.82-.64-.18-1.324-.267-2.004-.271-.68.003-1.364.091-2.003.269-1.528-1.035-2.2-.82-2.2-.82-.434 1.102-.16 1.915-.077 2.118-.512.56-.824 1.273-.824 2.147 0 3.064 1.867 3.751 3.645 3.954-.229.2-.436.552-.508 1.07-.457.204-1.614.557-2.328-.666 0 0-.423-.768-1.227-.825 0 0-.78-.01-.055.487 0 0 .525.246.889 1.17 0 0 .463 1.428 2.688.944v1.489c0 .211-.129.459-.528.385-3.18-1.057-5.472-4.056-5.472-7.59 0-4.419 3.582-8 8-8s8 3.581 8 8c0 3.533-2.289 6.531-5.466 7.59z"
              />
            </svg>
          </a>
          <!--Gmail-->
          <a href="mailto:azevedoerick762@gmail.com?CC=Olá" target="_blank">
            <svg
              class="icon"
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 24 24"
            >
              <path
                d="M12 .02c-6.627 0-12 5.373-12 12s5.373 12 12 12 12-5.373 12-12-5.373-12-12-12zm6.99 6.98l-6.99 5.666-6.991-5.666h13.981zm.01 10h-14v-8.505l7 5.673 7-5.672v8.504z"
              />
            </svg>
          </a>
      </div>
      <div class="text-container"> 
         <Title text="Contact" />

      <p>
        Pareço interessante? Se sim, vamos conversar. Seja sobre emprego, código, bitcoin, games ou o que quer que seja o assunto, o que aparecer eu topo. Aqui embaixo você pode ter acesso a minhas principais rede sociais.
      </p>
      </div>
    </div>
  </div>
</template>
<script>
import Title from "./widgets/Title.vue";
export default {
  components: {
    Title,
  },
};
</script>
<style scoped>
.icon {
  width: 50px;
  fill: rgb(218, 218, 218);
}
.contact {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 30px;
  flex-direction: column;
  background-color: #181b69;

} 
.social-handler{
  background-color: rgba(0, 0, 0, 0.938);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  align-content: center;
  margin-right:15px;
  min-width: 100px;
  width: 10%;
  padding: 3%;
  border-radius: 15px;
}
.social-handler > a{
  width: 50%;
}
.container-contact{
  background-color: #07082B;
  width: 60%;
  padding: 30px;
  border-radius: 15px;
  display: flex;
  flex-direction: row;
  min-height: 300px;
  justify-content: space-evenly;
  text-align: justify;
}
.text-container{
      font-family: 'Open Sans', sans-serif;
    font-size: 22px;
    color: #fff;
  width: 70%;
}
a{
  transition: 300ms;
}
a:hover{
  opacity: 0.8;
}
@media (max-width:630px){
    .container-contact{
        width: 95%;
      padding: 30px 0px;
    }
    .icon{
      width: 40px;
    }
      .social-handler{
        flex-direction: row;
        padding:45px;
        width: 40%;
      }
      .container-contact{
        flex-direction: column-reverse;
        justify-content: center;
        align-items: center;

      } 
      
      .text-container{
       margin-bottom:15px;
      }
    }
</style>
