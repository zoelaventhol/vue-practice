<!-- TEMPLATE 
    - This is the content we will see. 
    - We write it in HTML-->
<template>
    <div class="App">
        <h1>Picture time! 📸</h1>
        
        <!-- INPUT FORM -->
        <form>
            Add image: 
            <!-- Add v-model to save input as a variable in data -->
            <input type="text" v-model="url"/>
            <br />
            <!-- Add @click event handler. ".prevent" to prevent the page refreshing. -->
            <button @click.prevent="addImage">Submit</button>
        </form>

        <!-- Render component -->
        <ImageGrid :images="images" />
    </div>
</template>
    
<!-- SCRIPTS 
    - These will add data and functionality to our app.
    - We write them in Javascript. -->
<script>
    // import component (by file path)
    import ImageGrid from "./components/ImageGrid.vue";

    export default {
        //  The name of our component. It should match the file name.
        name: 'App',
        // This is where we list any components we import.
        components: {
            ImageGrid
        },
        // This is where we create variables (in the return statement)
        data() {
            return {
                // Add variables to save url from input, and to save all image urls together
                url: "",
                images: []
            }
        },
        // This is where we define our functions.
        methods: {
            addImage() {
                // push image url into the images array
                this.images.push(this.url);
                // reset the form to blank
                this.url = "";
            },
 
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

    input, button {
        margin-bottom: 2em;
    }

    .image-grid {
        /* set it up as a grid with 3 columns, and a gap between images */
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 1em;
        
        /* center it on the page */
        width: 50%;
        margin: auto;
    }

    img {
        /* standardize height */
        height: 150px;
        /* make everything square */
        aspect-ratio: 1;
        /* make sure image is cropped, not distorted */
        object-fit: cover;
        /* round the corners */
        border-radius: 10%;
    }
</style>