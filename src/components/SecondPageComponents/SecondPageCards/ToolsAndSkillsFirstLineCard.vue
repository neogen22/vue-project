<template>
    <link href="https://fonts.googleapis.com/css2?family=DM+Sans:opsz,wght@9..40,400;9..40,500&family=Outfit:wght@400;500&display=swap" rel="stylesheet">
    <div class="tool-flex-card-first-line-card" :style="{borderRadius: radius}">
        <img :src="image" :style="{width: widthOfSVG, height: heightOfSVG}">
        <div style="display: flex; flex-direction: column; row-gap: 1px; align-items: center;">
            <div class="name-of-technology">{{ technology }}</div>
            <div class="technology-for">{{ technologyFor }}</div>
        </div>
    </div>
</template>
<script>
export default {
    props: {
        technology: String,
        technologyFor: String,
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
        image: String,
    },
}
</script>
<style scoped>
    img {           
        align-self: center;
    }
    .tool-flex-card-first-line-card {
        display:flex; 
        flex-direction: column; 
        padding: 8px; 
        row-gap: 4px; 
        background-color: var(--gray-lightest-2, #F7F9FC); 
        height: 129px; 
        width: 227px; 
        box-sizing: border-box; 
        align-items: center; 
        justify-content: center;
    }
    .name-of-technology {        
        font-family: 'DM Sans', sans-serif;
        color: var(--Gray-Darker, #2E2E48);
        font-size: 14.118px;
        font-style: normal;
        font-weight: 500;
        line-height: 17px;
    }
    .technology-for {
        font-family: 'DM Sans', sans-serif;
        color: var(--Gray-Default, #79819A);
        text-align: center;
        font-size: 10.084px;
        font-style: normal;
        font-weight: 400;
        line-height: 12px;
        letter-spacing: 0.101px;
    }    
</style>