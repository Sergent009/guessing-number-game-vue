<template>
  <div class="container">
    <h2 :hidden="hidden">Guessing Number Game</h2>
    <button @click="clickMethod" :disabled="click" :hidden="hidden">Click If You Want To Play The Game</button>
  </div>

    <div class="mybox" v-show="click">
        <h2 class="header">Guess The Random Number</h2>
        <input placeholder="Enter Your Guess!" type="number" class="inputField" v-model="mynumber">
        <h1 v-if="mynumber === randomNumber">Congrats! You Guessed Correctly.</h1>
        <h1 v-if="mynumber < randomNumber">Go Higher!</h1>
        <h1 v-if="mynumber > randomNumber">Go Lower!</h1>
    </div>
</template>

<script>
export default {
    data(){
        return{
            click: false,
            hidden: false,
            mynumber: '',
            randomNumber: null
        }
    },

    methods:{
        clickMethod(){
            this.click = true
            this.hidden = true
            // it will generate a random number between 1 and 100
            this.randomNumber = Math.floor(Math.random() * 100) + 1
            console.log(this.randomNumber)
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
    cursor: pointer;
}

.mybox{
    width: 90vh;
    height: 60vh;
    background: white;
    position: absolute;
    top: 17%;
    left: 28%;
    border-radius: 20px;
}

.inputField{
    width: 60vh;
    height: 6vh;
    position: absolute;
    top: 25%;
    left: 16%;
    font-size: 19px;
    font-weight: 300;
    border: none;
    background: rgb(221, 217, 217);
    font-family: "Madimi One", sans-serif;
    border-radius: 3px;
    padding: 0px 15px;
    color: rgb(83, 83, 83);
}
.inputField:focus{
    background: white;
    font-weight: 500px;
    font-family: "Madimi One", sans-serif;
    /* it will remove the border outline */
    outline: none;
}

h1{
    width: 100%;
    height: 10%;
    position: absolute;
    top: 60%;
    left: 0%;
    font-weight: 500;
    background: grey;
    color: white;
    text-align: center;
}

.header{
    margin-top: 3%;
    width: 100%;
    height: 14%;
    position: absolute;
    top: 0;
    left: 0;
    background: rgb(61, 60, 60);
    color: white;
    font-weight: 500;
    text-align: center;
}



</style>