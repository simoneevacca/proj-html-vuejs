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
                    <p>Subscribe to be informed about important <br> velopments i our club and football world.</p>
                    <form action="">
                        <input type="email" placeholder="Your Email Address">
                        <button type="submit">Subscribe <i class="fa-solid fa-arrow-right-long"></i></button>
                    </form>
                </div>
                <div class="col col-3">
                    <h4>Education</h4>
                    <ul>
                        <li>
                            <div class="list-item"></div>FIXTURES & RESULTS
                        </li>
                        <li>
                            <div class="list-item"></div>LEAGUE TABLE
                        </li>
                        <li>
                            <div class="list-item"></div>PLAYERS
                        </li>
                        <li>
                            <div class="list-item"></div>GALLERY
                        </li>
                    </ul>
                </div>
                <div class="col col-3">
                    <h4>Quick Links</h4>
                    <ul>
                        <li>
                            <div class="list-item"></div>HOME
                        </li>
                        <li>
                            <div class="list-item"></div>BLOG
                        </li>
                        <li>
                            <div class="list-item"></div>GALLERY
                        </li>
                        <li>
                            <div class="list-item"></div>CONTACT
                        </li>
                    </ul>
                    
                </div>

            </div>

            <div class="copyright">&#169; 2022 Football Club - All Rights Reserved.</div>
        </div>
    </footer>
</template>

<style scoped>
footer {
    
    background-image: url("/images/footer-bg-football.jpg");

    & .container {
        width: 1408px;
        margin: auto;
        padding: 5rem 0 3rem 0;
        color: white;

        & .row {
            display: flex;
            width: 100%;

            & .col {
                color: white;
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
                > img {
                    width: 60px;
                }

                >div {
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

                >ul {
                    margin-top: 1.5rem;
                    list-style: none;

                    >li {
                        display: flex;
                        align-items: center;
                        gap: 8px;
                        margin-bottom: 1rem;

                        >.list-item {
                            width: 10px;
                            height: 3px;
                            background-color: white;
                        }
                    }
                }
            }

            & .col-5 {
                width: calc((100% / 12) * 5);
                display: flex;
                flex-direction: column;
                gap: 1.5rem;

                >form {
                    display: flex;
                    flex-direction: column;
                    width: 70%;
                    gap: 0.3rem;

                    >input,
                    button {
                        height: 3rem;
                        border-radius: 1.2rem;
                    }

                    >input {
                        padding-left: 1rem;
                    }

                    >button {
                        display: flex;
                        align-items: center;
                        justify-content: center;
                        gap: 5px;
                        cursor: pointer;
                    }
                }



            }


        }
        > .copyright {
            text-align: center;
            padding: 3rem 0 1rem 0;
        }
    }
}
</style>