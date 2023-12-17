<template>
    <link href="https://fonts.googleapis.com/css2?family=DM+Sans:opsz,wght@9..40,400;9..40,500&display=swap" rel="stylesheet">
    <div class="wrapper">
        <img :src="getImageUrl()" alt="">
        <div class="font">{{ name }}</div>
    </div>
</template>

<script>
    export default{
        props: {
            name: String,
            image: String,
        },
        methods: {
            getImageUrl() {
                return new URL(`../FirstPageIcons/${this.image}`, import.meta.url)
            }
        }
    }
</script>

<style scoped>
    img {
        width: 34px;
        height: 34px;
    }
    .font {        
        font-family: 'DM Sans', sans-serif;
        color: var(--Gray-Dark, #47516B);
        font-size: 14.118px;
        font-style: normal;
        font-weight: 500;
        line-height: 18.152px;
        align-self: center;
    }
    .wrapper {
        display: flex; 
        column-gap: 16.13px
    }
</style>