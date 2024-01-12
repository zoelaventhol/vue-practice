<!-- TEMPLATE 
    - This is the content we will see. 
    - We write it in HTML-->
<template>
    <div class="App">
        <h1>Hey FSPT26! 👋</h1>
        
        <!-- FORM -->
        Add image: <input v-model="url" type="url" />
        <br/>
        <button @click="addImage">Submit</button>

        <!-- IMAGE GRID -->
        <div class = "image-grid">
            <img 
                v-for="i in images"
                :src = "i"
            />
        </div>
    </div>
</template>
    
<!-- SCRIPTS 
    - These will add data and functionality to our app.
    - We write them in Javascript. -->
<script>
    export default {
        //  The name of our component. It should match the file name.
        name: 'App',
        // This is where we list any components we will import.
        components: {},
        // This is where we create variables (in the return statement)
        data() {
            return {
                url: "",
                images: []
            }
        },
        // This is where we define our functions.
        methods: {
            addImage () {
                console.log(this.url);
                // add the input url to images
                this.images.push(this.url);
                // reset input to bank
                this.url = ""
            }
        }
    }
</script>
    
<!-- STYLES
    - These will add style and formatting to our content.
    - We write it in CSS -->
<style>
    .App {
        margin: 0 auto;
        font-family: Arial, Helvetica, sans-serif;
        text-align: center;
    }

    button {
        margin-top: 1em;
        margin-bottom: 1em;
    }
</style>