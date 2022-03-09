<template>

  <h1>Contador</h1>
  <h2>{{counter}} <sup>2</sup> = {{squareCounter}} propiedad computed</h2>
  <h2>{{counter}} <sup>2</sup> = {{squareCounter}} propiedad computed</h2>
  <h2>{{counter}} <sup>2</sup> = {{squareCounter}} propiedad computed</h2>
  <h2>{{counter}} <sup>2</sup> = {{squareCounter}} propiedad computed</h2>
  <h2>{{esteban()}}</h2> 
  <h2>{{esteban()}}</h2> 

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

</style>