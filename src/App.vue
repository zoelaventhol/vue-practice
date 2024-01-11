<!-- TEMPLATE 
    - This is the content we will see. 
    - We write it in HTML-->
<template>
    <div class="App">
        <h1>Picture time! 📸</h1>
        
        <!-- INPUT FORM -->
        <form>
            Add image: 
            <input type="text" v-model="url"/>
            <br />
            <button @click.prevent="addImage">Submit</button>
        </form>

        <!-- IMAGE GRID -->
        <div class = "image-grid">
            (Images will go here)
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
            }
        },
        // This is where we define our functions.
        methods: {}
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

    input, button {
        margin-bottom: 1em;
    }
</style>