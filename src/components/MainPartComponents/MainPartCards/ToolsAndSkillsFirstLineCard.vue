<template>    
    <div class="tool-flex-card-first-line-card" :style="{borderRadius: radius}">
        <img :src="imageURL" :style="{width: widthOfSVG, height: heightOfSVG}" alt="">
        <div class="tool-flex-card-first-line-card-wrapper-inside">
            <span class="name-of-technology">{{ technology }}</span>
            <span class="technology-for">{{ technologyFor }}</span>
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
        radius: {
            type: String,
            default: "0px 0px 0px 0px"
        },
        widthOfSVG: {
            type: String,
            default: '48px',
        },
        heightOfSVG: {
            type: String,
            default: '48px',
        },
        image: {
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
    @media (orientation: portrait) {
        .tool-flex-card-first-line-card {
            display:flex; 
            flex-direction: column; 
            padding: 8px; 
            row-gap: 4px; 
            background-color: var(--gray-lightest-2, #F7F9FC);
            /* width: 85vw;  */
            box-sizing: border-box; 
            align-items: center; 
            justify-content: center;
        }
    }
    @media (orientation: landscape) {
        .tool-flex-card-first-line-card {
            display:flex; 
            flex-direction: column; 
            padding: 8px; 
            row-gap: 4px; 
            background-color: var(--gray-lightest-2, #F7F9FC);
            height: 129px;
            box-sizing: border-box; 
            align-items: center; 
            justify-content: center;
        }
    }    
    .name-of-technology {        
        font-family: 'DM Sans', sans-serif;
        color: var(--gray-darker, #2E2E48);
        font-size: 14px;
        font-style: normal;
        font-weight: 500;
        line-height: 17px;
    }
    .technology-for {
        font-family: 'DM Sans', sans-serif;
        color: var(--gray-default, #79819A);
        text-align: center;
        font-size: 10px;
        font-style: normal;
        font-weight: 400;
        line-height: 12px;
    }
    .tool-flex-card-first-line-card-wrapper-inside {
        display: flex; 
        flex-direction: column; 
        row-gap: 1px; 
        align-items: center;
    }

</style>