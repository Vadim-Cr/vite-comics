<script >

export default {
    name: "AppFooter",
    data() {
        return {
            images: [
                {
                    url: "../assets/images/buy-comics-digital-comics.png",
                    divContent: "DIGITAL COMICS",
                },
                {
                    url: "../assets/images/buy-comics-merchandise.png",
                    divContent: "DC MERCHANDISE",
                },
                {
                    url: "../assets/images/buy-comics-subscriptions.png",
                    divContent: "SUBSCRIPTION",
                },
                {
                    url: "../assets/images/buy-comics-shop-locator.png",
                    divContent: "COMIC SHOP LOCATOR",
                },
                {
                    url: "../assets/images/buy-dc-power-visa.svg",
                    divContent: "DC POWER VISA",
                },
            ],
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
        <div class="subContainerFooter"></div>
        <div class="subContainerFooter"></div>
        <div class="subContainerFooter"></div>
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
}

.subContainerFooterOne {
    width: 70%;
    margin: auto;
    align-items: center;
    height: 100%;
}

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
</style>
