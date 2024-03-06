<template>
  <div class="container">
    <h2 :hidden="hidden">Guessing Number Game</h2>
    <button @click="clickMethod" :disabled="click" :hidden="hidden">Click If You Want To Play The Game</button>
  </div>

   <div class="mybox" v-show="click">
    </div>
</template>

<script>
export default {
    data(){
        return{
            click: false,
            hidden: false
        }
    },

    methods:{
        clickMethod(){
            this.click = true
            this.hidden = true
            
        }
    }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Madimi+One&display=swap');

body{
    padding: 0;
    margin: 0;
    width: 100%;
    height: 100%;
    background-color: grey;
    font-family: "Madimi One", sans-serif;
}

h2{
    color: white;
    font-size: 40px;
    position: absolute;
    top: 5px;
    left: 470px;
}

button{
    position: absolute;
    top: 30%;
    left: 33%;
    padding: 5px 15px;
    font-size: 30px;
    font-family: "Madimi One", sans-serif;
    border-radius: 8px;
    color: rgb(83, 82, 82);
    background: white;
    border: 2px solid;
}

button:hover{
    color: green;
    background: rgb(182, 181, 181);
}

.mybox{
    /* width: 600px; */
    /* height: 400px; */
    width: 90vh;
    height: 60vh;
    background: white;
    position: absolute;
    top: 17%;
    left: 28%;
    border-radius: 20px;
}

</style>