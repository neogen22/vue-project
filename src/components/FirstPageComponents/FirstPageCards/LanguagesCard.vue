<template>
    <link href="https://fonts.googleapis.com/css2?family=DM+Sans:opsz,wght@9..40,400;9..40,500&family=Outfit:wght@400;500&display=swap" rel="stylesheet">
    <div class="wrapper">
        <img :src="getImageUrl()" alt="">
        <div class="wrapper-inside">
            <div class="language">{{ language }}</div>
            <div class="skill">{{ level }}</div>
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            language: String,
            level: String,
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
        height: 24px;
        width: 32px;
        border-radius: 4px;
    } 
    .language {        
        font-family: 'DM Sans', sans-serif;
        color: var(--Gray-Dark, #47516B);
        font-size: 14.118px;
        font-style: normal;
        font-weight: 500;
        line-height: 18.152px;
    }
    .skill {
        font-family: 'DM Sans', sans-serif;
        color: var(--Gray-Default, #79819A);
        font-size: 12.101px;
        font-style: normal;
        font-weight: 400;
        line-height: 16.135px;
        letter-spacing: 0.121px; 
    }    
    .wrapper {
        display: flex; 
        column-gap: 16.13px;
        align-self: stretch; 
        align-items: center;        
    }
    .wrapper-inside {
        display: flex; 
        flex-direction: column; 
        row-gap: 4px; 
        margin-top: -3px; 
        line-height: 8px;
    }
</style>