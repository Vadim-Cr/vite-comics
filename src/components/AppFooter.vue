<script >

export default {
    name: "AppFooter",
    data() {
        return {
            images: [
                {
                    url: "src/assets/images/buy-comics-digital-comics.png",
                    divContent: "DIGITAL COMICS",
                },
                {
                    url: "src/assets/images/buy-comics-merchandise.png",
                    divContent: "DC MERCHANDISE",
                },
                {
                    url: "src/assets/images/buy-comics-subscriptions.png",
                    divContent: "SUBSCRIPTION",
                },
                {
                    url: "src/assets/images/buy-comics-shop-locator.png",
                    divContent: "COMIC SHOP LOCATOR",
                },
                {
                    url: "src/assets/images/buy-dc-power-visa.svg",
                    divContent: "DC POWER VISA",
                },
            ],
            footerList: [
                {
                    name: "DC COMICS",
                    nameList: [
                        "Characters",
                        "comics",
                        "movies",
                        "TV",
                        "Games",
                        "Videos",
                        "News"
                    ],
                },
                {
                    name: "SHOP",
                    nameList: [
                        "Shop DC",
                        "Shop DC Collectibles",
                    ],
                },
                {
                    name: "DC",
                    nameList: [
                        "Terms Of Use",
                        "Privacy policy (NEW)",
                        "Add Choice",
                        "Advertising",
                        "Jobs",
                        "Subscriptions",
                        "Talent Workshops",
                        "CPSC Certificates",
                        "Ratings",
                        "Shop Help",
                        "Contact Us"
                    ],
                },
                {
                    name: "SITES",
                    nameList: [
                        "DC",
                        "MAD Magazine",
                        "DC Kids",
                        "DC Universe",
                        "DC Power Visa",
                    ],
                }
            ],
            socials: [
                {
                    url: "src/assets/images/footer-facebook.png",
                },
                {
                    url: "src/assets/images/footer-twitter.png",
                },
                {
                    url: "src/assets/images/footer-youtube.png",
                },
                {
                    url: "src/assets/images/footer-pinterest.png",
                },
                {
                    url: "src/assets/images/footer-periscope.png",
                },
            ]
        };
    },
}

</script>

<template>
    <footer>
        <div class="containerFooterOne">
            <div class="subContainerFooterOne">
                <ul>
                    <li v-for="(card, index) in images" :key="index">
                        <img :src="card.url" alt="">
                        <div class="text">
                            {{ card.divContent }}
                        </div>
                    </li>
                </ul>
            </div>
        </div>
        <div class="containerFooterTwo">
            <div class="subContainerFooterTwo">
                <div class="scfto">
                    <ul v-for="(listItem, indx) in footerList" :key="indx">
                        <a href="#">{{ listItem.name }}</a>
                        <li v-for="(item, i) in listItem.nameList" :key="i">
                            <a href="#">{{ item }}</a>
                        </li>
                    </ul>
                </div>
                <!-- <img src="../assets/images/dc-logo-bg.png" alt=""> -->
            </div>
        </div>
        <div class="subContainerFooterThree">
            <div class="subContainerFooterThree">
                <div class="scftl">
                    <button>SIGN-UP NOW !</button>
                </div>
                <div class="scftr">
                    <ul>
                        FOLLOW US
                        <li v-for="(media, ind) in socials" :key="ind">
                            <img :src="media.url" alt="">
                            <a href="#"></a>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
        <div class="subContainerFooterFour"></div>
    </footer>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixins' as *;

footer {
    height: 20rem;
}

.text {
    color: white;
    margin-left: 1rem;
}

.containerFooterOne {
    height: 7rem;
    background-color: $primary;

    .subContainerFooterOne {
        width: 70%;
        margin: auto;
        align-items: center;
        height: 100%;

        ul {
            list-style: none;
            height: 100%;
            @include center-between;

            li {
                @include center;
                margin: 0 1rem;

                img {
                    object-fit: contain;
                    height: 5rem;
                    width: 5rem;
                }

                &:hover {
                    background-color: #0564bc;
                    cursor: pointer;
                }

            }
        }
    }
}


.containerFooterTwo {
    background-image: url(../assets/images/footer-bg.jpg), url(../assets/images/dc-logo-bg.png);
    background-position: center, right top;
    background-repeat: no-repeat, no-repeat;
    background-size: cover, auto;
    height: 25rem;

    .subContainerFooterTwo {
        @include widthCenter;
        @include center-between;
        align-items: center;
        position: relative;
        height: 100%;


        .scfto {
            padding: 1rem;
            display: flex;
            flex-wrap: wrap;
            align-items: center;



            ul {
                list-style: none;
                font-weight: bold;
                font-size: 1.5rem;
                margin-right: 1rem;

                a {
                    text-decoration: none;
                    color: white;
                }

                li {
                    font-weight: 600;
                    font-size: 0.75rem;
                    margin-right: 1rem;

                    a {
                        text-decoration: none;
                        color: $fontPrimary;
                    }
                }
            }
        }


    }
}

.subContainerFooterThree {
    background-color: $secondary;
    height: 10rem;

    .subContainerFooterThree {
        @include center-between;
        @include widthCenter;
        z-index: 2;

        .scftl {
            button {
                background-color: #0564bc00;
                padding: 1rem;
                color: white;
                font-size: 1.1rem;
                border: 3px solid $primary;
            }
        }

        .scftr {
            z-index: 2;

            ul {
                @include center;
                list-style: none;
                color: $primary;
                font-weight: 600;
                font-size: 1.5rem;

                li {
                    padding: 0 1rem;

                    img:hover {
                        border: 3px solid $primary;
                        border-radius: 50%;
                        cursor: pointer;
                        background-color: white;
                    }
                }
            }
        }

    }

}

.subContainerFooterFour {
    background-color: $tertiary;
    height: 10rem;
}
</style>
