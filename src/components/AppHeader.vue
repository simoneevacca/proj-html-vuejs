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
            <div class="controller">
                <div :class="isVisible(index)" @click="prevImage" class="prev-button"><i class="fa-solid fa-chevron-left"></i></div>
                <div :class="isVisible(index)" @click="nextImage" class="next-button"><i class="fa-solid fa-chevron-right"></i></div>
    
            </div>
        </div>

    </header>

</template>

<style>

    header {

        & .slider{
            position: relative;
            & img.visible {
                width: 100%;
                /* height: 600px; */
                object-fit: cover;

            }


            & img:not(.visible) {
                display: none;
            }

            & .controller {
                width: 100%;
                position: absolute;
                top: 50%;
                transform: translate(0, -50%);
                display: flex;
                justify-content: space-between;
                color: white;

                & div:not(.visible){
                    display: none;
                }

                & .prev-button, .next-button {
                    display: flex;
                    align-items: center;
                    justify-content: center;
                    width: 6rem;
                    height: 6rem;
                    font-size: 2rem;
                    padding: 2rem;
                    margin: 3rem;
                    border: 3px solid white;
                    
                    border-radius: 50%;
                    
                    
                }
    
            }
        }


    }

</style>