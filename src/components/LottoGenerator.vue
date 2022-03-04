<template>
    
    <div class="container">
        <img src="../assets/pcso-logo.png" alt="vue-logo">
        <h1>My Lotto Generator</h1>
    </div>
    

    <button @click="lotto()">Generate Numbers</button>
    
    <div class="container1">
        <div class="show" v-for="digit in randomDigits" :key="digit">
            {{ digit }}
        </div>
    </div>
</template>


<script>
export default {
    data() {
        return {
            randomDigits : [],
            isPlaying : false
        }
    },
    methods: {
        lotto(){
            while(this.randomDigits.length < 6){
                let digits = Math.floor((Math.random() * 41)) + 1;
                if(!this.randomDigits.includes(digits)){
                    this.randomDigits.push(digits);
                }
            }
        }
    }
}
</script>

<style scoped>

.container{
     padding: 10px;
     margin-left: 30%;
    display: flex;
}
.container1{
    display: flex;
    margin-left: 26%;
    margin-right: 50%;
}
img{
    height: 100px;
    width: 50;
}
h1 {
    margin-left: 10px;
    font-size: 40px;
    font-family: Arial, Helvetica, sans-serif;
    color: black;
}
button{
    margin-bottom: 0px;
    margin-top: 10px;
    font-family: Arial, Helvetica, sans-serif;
    width: 320px;
    border-radius: 7px;
    box-shadow: 0px 5px 4px 2px #888888;
    height: 70px;
    font-size: 20px;
    margin-left: 0;
    margin-right: 0;
}
.show {
    padding: 20px;
    font-size: 70px;
    font-family: sans-serif;
    font-weight: bold;
    color: black;
}
</style>