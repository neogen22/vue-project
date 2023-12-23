<template>
    <link href="https://fonts.googleapis.com/css2?family=DM+Sans:opsz,wght@9..40,400;9..40,500&display=swap" rel="stylesheet">
    <div class="tool-flex-card" :style="{borderRadius: radius}">
        <img :src="getImageUrl()" :style="{width: widthOfSVG, height: heightOfSVG}">
        <div class="wrapper">
            <div class="first">{{ technology }}</div>
            <div class="last">{{ technologyFor }}</div>
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            technology: String,
            technologyFor: String,
            image: String,
            radius: {
                type: String,
                default: "0px 0px 0px 0px"
            },
            widthOfSVG: {
                type: String,
            },
            heightOfSVG: {
                type: String,
            }
        },
        methods: {
            getImageUrl() {
                return new URL(`../MainPartIcons/${this.image}`, import.meta.url)
            }
        },
    }
</script>

<style scoped>
    img {
        align-self: center;
    }    
    .first {        
        font-family: 'DM Sans', sans-serif;
        color: var(--Gray-Darker, #2E2E48);
        font-size: 14.118px;
        font-style: normal;
        font-weight: 500;
        line-height: 18.152px;
    }    
    .last {        
        font-family: 'DM Sans', sans-serif;
        color: var(--Gray-Default, #79819A);
        font-size: 10.084px;
        font-style: normal;
        font-weight: 400;
        line-height: 18px;
        letter-spacing: 0.101px; 
    }
    .tool-flex-card {
        display:flex;
        flex-direction: column;
        padding: 8px;
        row-gap: 4px;
        background-color: var(--gray-lightest-2, #F7F9FC);
        height: 113px;
        width: 133px;
        box-sizing: border-box;
        align-items: center;
        justify-content: center;
    }
    .wrapper {
        display: flex; 
        flex-direction: column; 
        column-gap: 1px; 
        align-items: center;
    }
</style>