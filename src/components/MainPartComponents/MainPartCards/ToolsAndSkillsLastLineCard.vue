<template>    
    <div class="tool-flex-card" :style="{borderRadius: radius}">
        <img :src="imageURL" :style="{width: widthOfSVG, height: heightOfSVG}" alt="">
        <div class="tool-flex-car-wrapper-inside">
            <span class="first">{{ technology }}</span>
            <span class="last">{{ technologyFor }}</span>
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
            radius: {
                type: String,
                default: "0px 0px 0px 0px"
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
    .first {        
        font-family: 'DM Sans', sans-serif;
        color: var(--gray-darker, #2E2E48);
        font-size: 14px;
        font-style: normal;
        font-weight: 500;
        line-height: 18px;
    }    
    .last {        
        font-family: 'DM Sans', sans-serif;
        color: var(--gray-default, #79819A);
        font-size: 10px;
        font-style: normal;
        font-weight: 400;
        line-height: 18px;
    }
    @media (orientation: portrait) {
        .tool-flex-card {
            display:flex;
            flex-direction: column;            
            row-gap: 4px;
            background-color: var(--gray-lightest-2, #F7F9FC);             
            height: 15vh;
            padding: 4px;
            box-sizing: border-box;
            align-items: center;
            justify-content: center;
        }
    }
    
    @media (orientation: landscape) {
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
    }
    .tool-flex-car-wrapper-inside {
        display: flex; 
        flex-direction: column; 
        column-gap: 1px; 
        align-items: center;
    }
</style>