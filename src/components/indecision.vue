<template>
    <img v-if="img" :src="img" alt=""> <!-- El v-if se encarga de revisar si la img existe, como inicia con null entonces no la muestra en el dom, :src="img" trae el link qu entrega la appi de la imagen -->
    <div class="bg-dark"> </div>
    <div class="indecision-container">

        <input v-model="question" type="text" placeholder="Hazme una pregunta" name="" id="">
        <p>Recuerda terminar con el signo de interrogación (?)</p>

        <div v-if="isValidQuestion"> <!-- en este caso muestra el div si isValidQuiestion es verdadera -->
            <h2>{{question}}</h2>
            <h1>{{answer}}</h1>
        </div>

    </div>
</template>


<script>
export default {
    data(){
        return{
            question:"casa",
            answer: null,
            img: null,
            isValidQuestion: false
        }
    },
    methods: {
        async getAnswer() {
            this.answer = "pensando..."
            const {answer, image} = await fetch("https://yesno.wtf/api").then(r=> r.json()) /* se realiza desestructuración del objeto que entrega la api */
            /* console.log(answer, image); */
            this.answer = answer === 'yes'? 'Si!' : 'No!' /* cambia la respuesta para que se vea en español */
            this.img = image
        }


    },

    watch: {
        question(value, oldvalue){

            this.isValidQuestion = false; /* Esta propiedad solo se hace verdadera al identificar el "?" y esto lo hace en la instrucción siguiente antes de esto continua en false esto se hace para ocultar el texto donde se encuentra question y answers */


            if(!value.includes("?")) return

            this.isValidQuestion = true;

            this.getAnswer()
                
            } 

        }
    }
    

</script>

<style>

    img, .bg-dark {
        height: 100vh;
        left: 0px;
        max-height: 100%;
        max-width: 100%;
        position: fixed;
        top: 0px;
        width: 100vw;
    }

    .bg-dark {
        background-color: rgba(0, 0, 0, 0.4);
    }

    .indecision-container {
        position: relative;
        z-index: 99;
    }
    
    input {
        width: 250px;
        padding: 10px 15px;
        border-radius: 5px;
        border: none;
    }
    input:focus {
        outline: none;
    }

    p {
        color: white;
        font-size: 20px;
        margin-top: 0px;
    }

    h1, h2 {
        color: white;
    }
    
    h2 {
        margin-top: 150px;
    }

</style>