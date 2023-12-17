<template>
    <link href="https://fonts.googleapis.com/css2?family=DM+Sans:opsz,wght@9..40,400;9..40,500&display=swap" rel="stylesheet">
    <div class="wrapper">
        <img :src="image" alt="">
        <div>
            <div class="social-media-name">{{ name }}</div>
            <div class="social-media-address">{{ address }}</div>
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            name: String,
            address: String,
            image: String
        }
    }
</script>

<style scoped>
    img {
        width: 32px;
        height: 32px;
        align-self: center;
    }
    .social-media-name {
        font-family: 'DM Sans', sans-serif;        
        color: var(--Gray-Default, #79819A);        
        font-size: 12.101px;
        font-style: normal;
        font-weight: 400;
        line-height: 16.135px;
        letter-spacing: 0.121px; 
    }
    .social-media-address {
        font-family: 'DM Sans', sans-serif;
        color: var(--Gray-Dark, #47516B);
        font-size: 14.118px;
        font-style: normal;
        font-weight: 500;
        line-height: 18.152px;
        text-decoration-line: underline; 
    }
    .wrapper {
        display: flex; 
        column-gap: 16.13px;
    }
</style>