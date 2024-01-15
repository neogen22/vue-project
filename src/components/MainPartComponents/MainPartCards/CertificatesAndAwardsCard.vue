<template>    
    <div class="certificates-and-awards-card">
        <img :src="imageURL" :style="{width: widthOfSVG, height: heightOfSVG}" alt="">
        <div class="certificates-and-awards-card-inside-wrapper">
            <span class="certificates-and-awards-card-first-child-font">{{ school }}</span>
            <span class="certificates-and-awards-card-last-child-font">{{ course }}</span>
        </div>
        <span class="certificates-and-awards-card-date-font">{{ dates }}</span>
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
                reacted: 0,
                imageURL: new URL(`/public/${this.image}`, import.meta.url),
                width: undefined
            }            
        },
        created() {
            this.width = window.innerWidth
            window.addEventListener('resize', () => {
                this.width = window.innerWidth
            })
        },
    }
</script>

<style scoped>
    .certificates-and-awards-card {
        display: flex; 
        flex-direction: row;
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
    @media screen and (min-width: 1190px) {
        .certificates-and-awards-card-inside-wrapper {
            display:flex; 
            flex-direction: column; 
            row-gap: 4px;
            width: 413px;
        }
    }
    @media screen and (min-width: 950px) and (max-width: 1189px)  {
        .certificates-and-awards-card-inside-wrapper {
            display:flex;
            flex-direction: column;
            row-gap: 4px;
            width: 227px;
        }
    }
    @media screen and (min-width: 300px) and (max-width: 950px)  {
        .certificates-and-awards-card {
            padding: 8px 12px;
            width: 332px;
            column-gap: 8px;
        }
        .certificates-and-awards-card-inside-wrapper  {
            display: grid;
            column-gap: 8px;
            row-gap: 8px;
            width: 127px;
        }
        .certificates-and-awards-card-last-child-font {            
            text-wrap: nowrap;
        }
        .certificates-and-awards-card-date-font {
            padding: 0;
            width: 150px
        }
    }
</style>