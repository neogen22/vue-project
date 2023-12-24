<template>
    <link href="https://fonts.googleapis.com/css2?family=DM+Sans:opsz,wght@9..40,400;9..40,500&family=Outfit:wght@400;500&display=swap" rel="stylesheet">
    <div class='wrapper' :style="{borderRadius: radius}">
        <div style="display: flex; flex-direction: row; column-gap: 16px;">
            <img :src="imageURL" width="48px" height="48px" alt="">
            <div style="display: flex; flex-direction: column; row-gap: 4px; width: 230px; height: auto;">
                <span class="latests-project-font-first-line">{{ first }}</span>
                <span class="latests-project-font-last-line">{{ last }}</span>
            </div>
        </div>
        <div style="display: flex; flex-direction: row; column-gap: 12px;" :style="{paddingTop: paddingTopElement}">
            <img :src="secondImageURL" width="24px" height="24px" alt="">
            <a :href="HTMLAddress"><span class="latest-projects-card-font-first-line">{{ url }}</span></a>
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            first: {
                type: String,
                required: true
            },
            last: {
                type: String,
                required: true
            },
            url: {
                type: String,
                required: true
            },
            image: {
                type: String,
                required: true
            },
            secondImage: {
                type: String,
                required: true
            },
            paddingTopElement: {
                type: String,
                required: true
            },
            radius: {
                type: String,
                default: "0px 0px 0px 0px"
            },
            HTMLAddress: {
                type: String,
                required: true
            }
        },            
        data() {
            return {
                imageURL: new URL(`/public/${this.image}`, import.meta.url),
                secondImageURL: new URL(`/public/${this.secondImage}`, import.meta.url),
            }
        }
    }
</script>

<style scoped>
    a {
        padding: 0;
        margin: 0;
        border: 0;
	      vertical-align: baseline;
        line-height: 0;
    }
    .latests-project-font-first-line{        
        font-family: 'DM Sans', sans-serif;
        color: var(--gray-darker, #2E2E48);
        font-size: 16px;
        font-style: normal;
        font-weight: 500;
        line-height: 20px;
    }
    .latests-project-font-last-line {        
        font-family: 'DM Sans', sans-serif;
        color: var(--gray-default, #79819A);
        font-size: 14px;
        font-style: normal;
        font-weight: 400;
        line-height: 18px;
        text-overflow: clip;
    }
    .latest-projects-card-font-first-line {        
        font-family: 'Outfit', sans-serif;
        color: var(--secondary-default, #516CF7);
        font-size: 16px;
        font-style: normal;
        font-weight: 600;
        line-height: 20px;
        text-decoration-line: underline; 
    }
    .wrapper {
        display: flex; 
        flex-direction: column; 
        width: 343px; 
        background-color: var(--gray-lightest-2, #F7F9FC);  
        padding: 24px;
        box-sizing: border-box;
    }
</style>