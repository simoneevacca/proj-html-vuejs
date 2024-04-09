<script>
export default {
    name: 'AppFooter'
}
</script>


<template>


    <footer>
        <div class="container">
            <div class="row">
                <div class="col col-3">
                    <img src="/images/logo-footer-football.png" alt="">
                    <div><i class="fa-solid fa-location-dot"></i> New Jersey, USA</div>
                    <div><i class="fa-solid fa-phone-volume"></i> +1 (234) 567 89 10</div>
                    <div><i class="fa-solid fa-envelope"></i> example@example.com</div>
                    <div class="social">
                        <a href=""><i class="fa-brands fa-facebook-f"></i></a>
                        <a href=""><i class="fa-brands fa-instagram"></i></a>
                        <a href=""><i class="fa-brands fa-twitter"></i></a>
                    </div>
                </div>

                <div class="col col-5">
                    <h4>Join Our Newsletter</h4>
                </div>
                <div class="col col-2">
                    <h4>Education</h4>
                </div>
                <div class="col col-2">
                    <h4>Quick Links</h4>
                </div>

            </div>
        </div>
    </footer>
</template>

<style scoped>
footer {
    height: 500px;
    background-image: url("/images/footer-bg-football.jpg");

    & .container {
        width: 1408px;
        margin: auto;
        padding-top: 3rem;

        & .row {
            display: flex;
            width: 100%;

            & .col {
                color: white;
                
                border: 1px solid white;

                & i {
                    font-size: 1.5rem;
                    margin-right: 0.4rem;
                }
                & h4 {
                    font-size: 1.8rem;
                }
            }

            & .col-3 {
                width: calc((100% / 12) * 3);
                > div {
                    margin-top: 1rem;
                }
                >.social {
                    display: flex;

                    >a {
                        color: white;
                        text-decoration: none;
                        >i {
                            border: 1px solid white;
                            width: 50px;
                            height: 35px;
                            display: flex;
                            justify-content: center;
                            align-items: center;
                        }

                    }
                }
            }

            & .col-5 {
                width: calc((100% / 12) * 5);
                
            }

            & .col-2 {
                width: calc((100% / 12) * 2);
            }
        }
    }
}
</style>