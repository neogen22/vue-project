<template>
    <link href="https://fonts.googleapis.com/css2?family=DM+Sans:opsz,wght@9..40,400;9..40,500&display=swap" rel="stylesheet">
    <div class="wrapper">
        <img :src="image" alt="">
        <span class="font">{{ name }}</span>
    </div>
</template>

<script>
    export default{
        props: {
            name: {
                type: String,
                required: true,
            },
            image: {
                type: String,
                required: true,
            },
        },
        methods: {
            getImageUrl() {
                return new URL(`../AsideIcons/${this.image}`, import.meta.url)
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