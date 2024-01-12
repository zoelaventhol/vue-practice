<!-- TEMPLATE 
    - This is the content we will see. 
    - We write it in HTML-->
<template>
    <div class="App">
        <h1>Hey FSPT26! 👋</h1>
        
        <button @click="showForm = !showForm">
            <p v-if="showForm">Hide form</p>
            <p v-else>Add images!</p>
        </button>

        <!-- FORM -->
        <form v-if="showForm">
            Add image: <input v-model="url" type="url" />
            <br/>
            <button @click.prevent="addImage">Submit</button>
        </form>

        <!-- IMAGE GRID -->
        <ImageGrid 
            :images="images"
        />
    </div>
</template>
    
<!-- SCRIPTS 
    - These will add data and functionality to our app.
    - We write them in Javascript. -->
<script>
    import ImageGrid from "./components/ImageGrid.vue"

    export default {
        //  The name of our component. It should match the file name.
        name: 'App',
        // This is where we list any components we will import.
        components: {
            ImageGrid
        },
        // This is where we create variables (in the return statement)
        data() {
            return {
                url: "",
                images: [],
                showForm: false
            }
        },
        // This is where we define our functions.
        methods: {
            addImage () {
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

    .image-grid {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 1em;
        width: 50%;
        margin: auto;
    }

    img {
        height: 150px;
        aspect-ratio: 1;
        object-fit: cover;
        border-radius: 10%;
    }

</style>