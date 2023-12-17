<template>
    <link href="https://fonts.googleapis.com/css2?family=DM+Sans:opsz,wght@9..40,400;9..40,500&family=Outfit:wght@400;500&display=swap" rel="stylesheet">
    <div class='wrapper' :style="{borderRadius: radius}">
        <div style="display: flex; flex-direction: row; column-gap: 16.13px;">
            <img :src="secondImage" width="48px" height="48px">
            <div style="display: flex; flex-direction: column; row-gap: 4.03px; width: 230px; height: auto;">
                <div class="latests-project-font-first-line">{{ first }}</div>
                <div class="latests-project-font-last-line">{{ last }}</div>
            </div>
        </div>
        <div style="display: flex; flex-direction: row; column-gap: 12.1px;" :style="{paddingTop: paddingTopElement}">
            <img :src="image" width="24px" height="24px">
            <div class="latest-projects-card-font-first-line">{{ url }}</div>
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            first: String,
            last: String,
            url: String,
            image: String,
            secondImage: String,
            paddingTopElement: String,
            radius: {
                type: String,
                default: "0px 0px 0px 0px"
            }
        }
    }
</script>

<style scoped>
    .latests-project-font-first-line{        
        font-family: 'DM Sans', sans-serif;
        color: var(--Gray-Darker, #2E2E48);
        font-size: 16.135px;
        font-style: normal;
        font-weight: 500;
        line-height: 20.168px;
    }
    .latests-project-font-last-line {        
        font-family: 'DM Sans', sans-serif;
        color: var(--Gray-Default, #79819A);
        font-size: 14.118px;
        font-style: normal;
        font-weight: 400;
        line-height: 18.152px;
        letter-spacing: 0.141px;
        text-overflow: clip;
    }
    .latest-projects-card-font-first-line {        
        font-family: 'Outfit', sans-serif;
        color: var(--Secondary-Default, #516CF7);
        font-size: 16.135px;
        font-style: normal;
        font-weight: 600;
        line-height: 20.168px;
        text-decoration-line: underline; 
    }
    .wrapper {
        display: flex; 
        flex-direction: column; 
        width: 343px; 
        background-color: var(--gray-lightest-2, #F7F9FC);  
        padding: 24.2px;
        box-sizing: border-box;
        
    }
</style>