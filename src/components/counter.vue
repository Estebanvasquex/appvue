<template>

  <h1>{{customTitle}}</h1>
  <h2>{{counter}} <sup>2</sup> = {{squareCounter}} propiedad computed</h2>

  <div>
      <button @click="increase">+1</button>
      <button @click="decrease">-1</button>
  </div>


  <span> </span>
 

</template>

<script>
export default {
    props: {
        tituloCompo: String,
        start:{
             type: Number,
             default: 101,
             validator(value){
                 return value > 100
             }

        }

        },
        
    

    data() {
        return {
            counter: this.start
            
        }
    },
    methods:{
        esteban(){
            return 'Propieda enviada desde methods'
        },
        increase(){
            this.counter =  this.counter + 1
        },
        decrease(){
            this.counter = this.counter - 1
        }
        


    },

    computed: {
        squareCounter () {
            console.log('computed property')
            return this.counter * this.counter
        },
        customTitle(){

            return this.tituloCompo  || 'Counter'
             //si titulo campo esta sin dato por defecto le da Counter
            // return this.tituloCompo ? this.title : 'Counter' Esto es un ternario

        },

        customStart(){

            return this.start  || 1
             //si start campo esta sin dato le pone 1 
            // return this.tituloCompo ? this.title : 'Counter' Esto es un ternario

        }
    }

}
</script>

<style>
button{
    background-color: #64B687;
    border-radius: 5px;
    padding: 20px;
    font-size: 20px;
    border: 1px solid white;
    color: white;
    cursor: pointer;
    margin: 0 5px;
    margin: 5px;
    transition: 0.3s ease-in-out;
}

button:hover{
    background-color: #5aa67b;
    transition: 0.3s ease-in-out;

}
</style>