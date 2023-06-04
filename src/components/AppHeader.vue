<script >

export default {
    name: "AppHeader",
    data() {
        return {
            navList: [
                "CHARACTER", "COMICS", "MOVIES", "TV", "GAMES", "COLLECTIBLES", "VIDEOS", "FANS", "NEWS", "SHOP"
            ],
        }
    }
}

</script>

<template>
    <header>
        <div class="container_header">
            <img src="../assets/images/dc-logo.png" alt="">
            <div class="subContainerHeader">
                <ul>
                    <li v-for="(item, index) in navList" :key="index">
                        <a href="">
                            {{ item }}
                        </a>
                    </li>
                </ul>
            </div>
        </div>

    </header>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixins' as *;

header {
    width: 70%;
    margin: auto;
    padding: 1rem 0;
    text-align: center;
    height: 10rem;
    @include center;
}

.container_header {
    @include center-between;
    width: 100%;

    img {
        margin-left: 2rem;
    }
}

ul {
    padding: 0 2rem;
    list-style: none;
    @include center;

    li {
        padding: 1rem;
        font-weight: 600;

        a {
            text-decoration: none;
            color: $fontPrimary;
            font-size: 0.75rem;

            &:hover {
                color: $primary;
                border-bottom: 3px solid $primary;
                padding-bottom: 3.8rem;
            }
        }

    }
}
</style>
