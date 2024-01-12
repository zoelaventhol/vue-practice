<!-- TEMPLATE 
    - This is the content we will see. 
    - We write it in HTML-->
    <template> 
        <!-- BUTTONS -->
        <button :class="{active : isBig}" @click="toggle(true)">Big</button>
        <button :class="{active : !isBig}" @click="toggle(false)">Small</button>
    
        <!-- IMAGE GRID -->
        <div class = "image-grid">
            <img 
                v-for="i in images"
                :src = "i"
                :class="{big : isBig}"
            />
        </div>
    </template>
        
    <!-- SCRIPTS 
        - These will add data and functionality to our app.
        - We write them in Javascript. -->
    <script>
        export default {
            //  The name of our component. It should match the file name.
            name: 'ImageGrid',
            // This is where we list any components we will import.
            components: {},
            // This is where we create variables (in the return statement)
            data() {
                return {
                    isBig: false
                }
            },
            // This is where we define our functions.
            methods: {
               toggle(state) {
                this.isBig = state
               } 
            },
            props: ['images']
        }
    </script>
        
    <!-- STYLES
        - These will add style and formatting to our content.
        - We write it in CSS -->
    <style> 
      .active {
        color:red;
        border: 2px solid red;
      } 

      .big {
        height: 300px;
      }
    </style>