<script>
   export default{
    data(){
        return{
            mensaje:"Hola Vue",
            descripcion:"<h1>Esto se carga desde vue</h1>",
            mostrar:true,
            nombre:"Senki",
            edad:47548898328328329,
            Gokaiger:"https://img06.deviantart.net/fca1/i/2011/326/2/3/kaizoku_sentai_gokaiger_by_blakehunter-d4gyf3s.jpg"

        }

    }
}

</script>


<template>
   <h1 v-text="mensaje"></h1>
   <div v-html="descripcion"></div>
   <p v-if="edad">=18>
        
     Eres mayor de edad  

   </p>

   <p v-else-if="edad<18">
      Eres menor de edad
   </p>

   <p v-show="mostrar">

    Este texto puede estar oculto

   </p>

   <img :src="Gokaiger" alt="">

</template>



<style scoped>

</style>