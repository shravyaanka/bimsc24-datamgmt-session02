<!-- the script is where the js code goes -->
<script setup>
import { ref } from "vue" // you need this to use ref()

let count = ref(0);
let scriptName = ref ("addTwoNumbers.gh")
let name = ref("Shravya's")

function increment() { 
    count.value++;

}


const mainColor = ref('#ffffff'); // Initial color for the main content
const newColor = ref(''); // Variable to store the color from the text box

const changeMainColor = () => {
  // Update the mainColor with the value from the text box
  mainColor.value = newColor.value;
};


const textInput = ref('');
const textList = ref([]);

function addText() {
  textList.value.push(textInput.value);
  // Optionally, you can clear the input after adding text
  // textInput.value = '';
}


</script>

<!-- the template is where the html code goes -->
<template>
   
   <div id="navbar" class="container">  
        <div id="title">{{name}} first website</div>
        
        <div id="logo">
            <img src="./cow.jpg" alt="macad cow">

        </div>
        

    </div>

    <div id="flex">

        <div id="sidebar" > Sidebar 

            <div id="buttons1">

                <button @click="increment">Add one more</button>

            </div>


            <div id="buttons2">
                <button @click="changeMainColor">Change Main Color</button>
                <input v-model="newColor" type="text" placeholder="Enter Color" />
            </div>


            <div id="buttons3">
                <button @click="addText">Add Text</button>
                <input v-model="textInput" type="text" placeholder="Enter Text" />
            </div>



        </div>

        

        <div id="main" :style="{ backgroundColor: mainColor }"> Main Area 

            <p style= "margin-left: 20px" >Count is: {{count}}</p>

            <!-- Display all added texts -->
            <p v-for="(text, index) in textList" :key="index" style="margin-left: 20px">
                Text added: {{ text }}
            </p>

                
            </div>




    </div>

    
    

</template>



<!-- style is where the css code goes -->
<style scoped>
html{
    
    background-color: rgb(106, 57, 104); 
    color: rgb(246, 250, 250);
}

body{

    margin:0;
}

div{

    /* put the borders in the inside of container */
    box-sizing: border-box;
}

img{

    height: 100%;
    width: auto;

}

#navbar{

    height: 50px;
    border-color: rgb(38, 219, 207);
    background-color: rgb(45, 104, 82);
    padding: 2%;
    display: flex;
    flex-direction:column;
    text-align: center;
    font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
    font-size: x-large;
    font-style: bold;
    


}

#flex{
    
    display: flex;
    height: calc(100vh - 50px);
}

#sidebar{

    width: 60%;
    border-color: rgb(13, 13, 14);
    background-color: rgb(123, 197, 137);
    padding: 8px;
    

}

#buttons1{

    display: flex;
    justify-content: right;
    margin: 20px;

}

#buttons2{

display: flex;
justify-content: left;
margin: 10px;

}

#buttons3{

display: flex;
justify-content: left;
margin: 20px;

}



.center {

  width: 20%;
  padding: 10px;
  line-height: 100px;
  
}

#main{
    width: 40%;
    border-color: green;
    background-color: var(--mainColor);
    padding: 20px;
    flex: 1;

}

#title{
    width: 50%;
    float:center;
}

#logo{
    width: 50%;
    height: 100%;
    float:left;
    text-align: right;

}

.button {
  margin-bottom: 10px;
}

.container{

    border-style: dotted;
    border-width: 1px;

}


</style>