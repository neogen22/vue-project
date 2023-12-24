<template>
    <link href="https://fonts.googleapis.com/css2?family=DM+Sans:opsz,wght@9..40,400;9..40,500&display=swap" rel="stylesheet">
    <div class="certificates-and-awards-card" :style="{borderRadius: radius}">
        <img :src="imageURL" :style="{width: widthOfSVG, height: heightOfSVG}" alt="">
        <div class="wrapper">
            <div class="certificates-and-awards-card-first-child-font">{{ school }}</div>
            <div class="certificates-and-awards-card-last-child-font">{{ course }}</div>        
        </div>
        <div class="certificates-and-awards-card-date-font">{{ dates }}</div>
    </div>
</template>

<script>
    export default {
        props: {
            school: {
                type: String,
                required: true
            },
            course: {
                type: String,
                required: true
            },
            dates: {
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
        },
    }
</script>

<style scoped>
    .certificates-and-awards-card { 
        display: flex; 
        flex-direction: row;
        width: 642px;
        column-gap: 12px;
        padding: 16px 23px;
        box-sizing: border-box; 
        background-color: var(--gray-lightest-2, #F7F9FC);
    }
    .certificates-and-awards-card-first-child-font {        
        font-family: 'DM Sans', sans-serif;
        color: var(--gray-default, #79819A);
        font-size: 14px;
        font-style: normal;
        font-weight: 400;
        line-height: 17px;
    }
    .certificates-and-awards-card-last-child-font {        
        font-family: 'DM Sans', sans-serif;
        color: var(--gray-darker, #2E2E48);
        font-size: 16px;
        font-style: normal;
        font-weight: 500;
        line-height: 19px;
    }
    .certificates-and-awards-card-date-font {        
        font-family: 'DM Sans', sans-serif;
        color: var(--gray-dark, #47516B);
        font-size: 12px;
        font-style: normal;
        font-weight: 400;
        line-height: 16px;
        width: 117px
    }
    .wrapper {
        display:flex; 
        flex-direction: column; 
        row-gap: 4px;
        width: 413px;
    }
</style>