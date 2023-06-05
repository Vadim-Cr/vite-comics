<script >

export default {
    name: "AppMain",
    props: {
        siteCards: Array,
    }
}

</script>   

<template>
    <main>
        <div class="container">
            <div v-for="(comic, index) in siteCards" :key="index" class="subContainer">
                <img :src="comic.thumb" alt="">
                <div class="price">
                    {{ comic.price }}
                </div>
                <div class="series">
                    {{ comic.series }}
                </div>
                <div class="type">
                    {{ comic.type }}
                </div>
            </div>
        </div>
    </main>
</template>




<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixins' as *;

main {
    background-color: $tertiary;
    min-height: 10rem;

    .container {
        @include center;
        flex-wrap: wrap;
        @include widthCenter;

        .subContainer {
            padding: 1rem;
            width: calc(100% / 6);

            .price,
            .series,
            .type {
                @include textCardMain;

                &:hover {
                    font-size: 1.5rem;
                    color: $primary;
                    border-bottom: 3px solid white;
                }
            }

            img {
                object-fit: contain;
                height: 12rem;

                &:hover {
                    filter: brightness(1.35);
                    border: 3px solid $primary;
                }
            }
        }

    }
}
</style>