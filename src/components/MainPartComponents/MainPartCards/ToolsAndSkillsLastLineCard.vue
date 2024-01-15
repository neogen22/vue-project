<template>    
    <div class="tool-flex-card-last-line-card">
        <img :src="imageURL" :style="{width: widthOfSVG, height: heightOfSVG}" alt="">
        <div class="tool-flex-card-last-line-card-wrapper-inside">
            <span class="tool-flex-card-last-line-card-wrapper-inside-first-item">{{ technology }}</span>
            <span class="tool-flex-card-last-line-card-wrapper-inside-last-item">{{ technologyFor }}</span>
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            technology: {
                type: String,
                required: true
            },
            technologyFor: {
                type: String,
                required: true
            },
            image: {
                type: String,
                required: true
            },
            widthOfSVG: {
                type: String,
                required: true
            },
            heightOfSVG: {
                type: String,
                required: true
            },
        },
        data() {
            return {
                imageURL: new URL(`/public/${this.image}`, import.meta.url)
            }
        }
    }
</script>

<style scoped>
    img {
        align-self: center;
    }    
    .tool-flex-card-last-line-card-wrapper-inside-first-item {
        font-family: 'DM Sans', sans-serif;
        color: var(--gray-darker, #2E2E48);
        font-size: 14px;
        font-style: normal;
        font-weight: 500;
        line-height: 18px;
    }    
    .tool-flex-card-last-line-card-wrapper-inside-last-item {
        font-family: 'DM Sans', sans-serif;
        color: var(--gray-default, #79819A);
        font-size: 10px;
        font-style: normal;
        font-weight: 400;
        line-height: 18px;
    }
    
    .tool-flex-card-last-line-card {
        display:flex;
        flex-direction: column;
        padding: 8px;
        row-gap: 4px;
        background-color: var(--gray-lightest-2, #F7F9FC);
        height: 113px;            
        box-sizing: border-box;
        align-items: center;
        justify-content: center;
    }    
    .tool-flex-card-last-line-card-wrapper-inside {
        display: flex; 
        flex-direction: column; 
        column-gap: 1px; 
        align-items: center;
    }
</style>