<template>

  <h1>Contador</h1>
  <h2>{{counter}} <sup>2</sup> = {{squareCounter}} propiedad computed</h2>
  <h2>{{counter}} <sup>2</sup> = {{squareCounter}} propiedad computed</h2>
  <div>
      <button @click="increase">+1</button>
      <button @click="decrease">-1</button>
  </div>


  <span> </span>
 

</template>

<script>
export default {
    data() {
        return {
            counter:5
        }
    },
    methods:{
        esteban(){
            console.log('esteban')
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
        }
    }

}
</script>

<style>
button{
    background-color: #64B687;
    border-radius: 5px;
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