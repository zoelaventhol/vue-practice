<template>
    <div class="ImageGrid">
        <!-- IMAGE GRID -->
        <div class = "image-grid">
            <!-- Create an <img> tag for each of your URLs using a v-for loop. Set your URL as the src attribute. -->
            <img v-for="url in images" 
                :src = "url"
            />

        </div>
    </div>
</template>
    
<script>
    export default {
        name: 'ImageGrid',
        components: {},
        data() {
            return {
            }
        },
        methods: {
        },
    }
</script>
    
<style>
</style>