<script>
    export default {
        name: 'AppHeader',
        data() {
            return {
                visibleImage: 0,
                
                slider: [
                    '/images/slider1-1.jpg',
                    '/images/slider2-1.jpg',
                    '/images/slider3.jpg',
                    '/images/slider4.jpg',
                ]
            }
        },
        methods: {
            isVisible (value){
                if(value === this.visibleImage){
                    return 'visible'
                }
            },

            nextImage () {
                this.visibleImage ++
                if (this.visibleImage == this.slider.length) {
                    this.visibleImage = 0 
                }
            },

            prevImage () {
                if (this.visibleImage == 0) {
                    this.visibleImage = this.slider.length 
                }
                this.visibleImage --
            }
        }
    }
    
</script>

<template>
    <header>

        <div class="slider" v-for="(image, index) in slider">
            <img :class="isVisible(index)" :src="slider[index]" alt="">
        </div>
        <div class="controller">
            <div @click="nextImage" class="next-button"> next </div>
            <div @click="prevImage" class="prev-button"> prev </div>

        </div>

    </header>

</template>

<style>

    header {


        & img:not(.visible) {
            display: none;
        }
    }

</style>