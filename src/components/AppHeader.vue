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
            ],
            autoplay: null
        }
    },
    methods: {
        isVisible(value) {
            if (value === this.visibleImage) {
                return 'visible'
            }
        },

        nextImage() {
            this.visibleImage++
            if (this.visibleImage == this.slider.length) {
                this.visibleImage = 0
            }
        },

        prevImage() {
            if (this.visibleImage == 0) {
                this.visibleImage = this.slider.length
            }
            this.visibleImage--
        },

        startAutoplay() {
            this.autoplay = setInterval(() => {
                this.nextImage();
            }, 3000)
        },

        stopAutoplay() {
            clearInterval(this.autoplay)
        }
    }
}

</script>

<template>
    <header>

        <nav>
            <div class="container">
                <div class="logos">
                    <img src="/images/sponsor1.png" alt="">
                    <img src="/images/sponsor2.png" alt="">
                    <img src="/images/logo-football.png" alt="">
                    <i class="fa-brands fa-facebook-f"></i>
                    <i class="fa-brands fa-instagram"></i>
                    <i class="fa-brands fa-twitter"></i>
                </div>
                <ul class="link">
                    <li><a href="">HOME</a></li>
                    <li><a href="">FUXTURES & RESULTS</a></li>
                    <li><a href="">LEAGUE TABLE</a></li>
                    <li><a href="">PLAYERS</a></li>
                    <li><a href="">GALLERY</a></li>
                    <li><a href="">BLOG</a></li>
                    <li><a href="">CONTACT</a></li>
                </ul>
                <div class="menu"><a href=""><i class="fa-solid fa-bars-staggered"></i></a></div>
            </div>
        </nav>

        <section class="jumbotron">
            <h1>Football Club</h1>
            <h1>Sport Club</h1>
            <h3>Private football matches</h3>
            <div class="button">
                <div>Learn More</div>
                <i class="fa-solid fa-arrow-right-long"></i>
            </div>
        </section>


        <div class="slider" v-for="(image, index) in slider" @mouseenter="startAutoplay" @mouseleave="stopAutoplay">
            <img :class="isVisible(index)" :src="slider[index]" alt="">
            <div class="controller">
                <div :class="isVisible(index)" @click="prevImage" class="prev-button"><i
                        class="fa-solid fa-chevron-left"></i></div>
                <div :class="isVisible(index)" @click="nextImage" class="next-button"><i
                        class="fa-solid fa-chevron-right"></i></div>

            </div>
        </div>

    </header>

</template>

<style>
header {
    & :hover {
        cursor: url('/images/custom-pointer.png') 42 42, auto;

    }

    nav {
        position: absolute;
        top: 0px;
        z-index: 1;
        width: 100%;
        background-color: rgba(0, 0, 0, 0.693);
        padding: 0.5rem 0 2rem 0;

        & .container {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 1rem;

            & .logos {
                color: white;
                display: flex;
                align-items: center;

                & i {
                    font-size: 2rem;
                    padding: 0 0 0 1rem;
                }
            }

            & .link {
                display: flex;
                list-style: none;
                gap: 3rem;

                & li {
                    padding-bottom: 5px;
                    border-bottom: 3px solid;
                    transition: 0.3s;
                }

                & li:hover {
                    border-bottom: 3px solid white;


                }



                & a {
                    color: white;
                    text-decoration: none;
                    font-weight: bold;
                }
            }

            & .menu {
                align-self: flex-end;
                margin-top: -2rem;
                padding-right: 1rem;

                & a {
                    font-size: 2rem;
                    color: white;
                }
            }
        }
    }


    & .jumbotron {
        z-index: 1;
        position: absolute;
        bottom: 0px;
        left: 50%;
        transform: translate(-50%, -0%);
        color: white;
        text-align: center;
        display: flex;
        flex-direction: column;
        align-items: center;


        & h1 {
            font-size: 5rem;
        }

        & h3 {
            font-size: 1.5rem;
            padding: 2rem;
        }

        & .button {
            display: flex;
            justify-content: center;
            align-items: self-end;
            gap: 0.3rem;
            border: 2px solid white;
            width: 50%;
            font-size: 1.2rem;
            font-weight: bold;
            padding: 1.5rem 0;
            border-radius: 30px;
        }

    }




    & .slider {
        z-index: 0;
        position: relative;

        & img.visible {
            width: 100%;
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

            & div:not(.visible) {
                display: none;
            }

            & .prev-button,
            .next-button {
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