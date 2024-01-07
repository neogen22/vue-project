<template>    
    <div class='latest-project-card-wrapper' :style="{borderRadius: radius}">
        <div class="wrapper-inside">
            <img :src="imageURL" width="48px" height="48px" alt="">
            <div style="" class="wrapper-inside-second">
                <span class="latests-project-font-first-line">{{ first }}</span>
                <span class="latests-project-font-last-line">{{ last }}</span>
            </div>
        </div>
        <div v-if="!portrait" :style="{paddingTop: paddingTopElement}" class="wrapper-inside-third">
            <img :src="secondImageURL" width="24px" height="24px" alt="">
            <a :href="HTMLAddress" class="latest-projects-card-font-first-line">{{ url }}</a>
        </div>
        <div v-else class="wrapper-inside-third">
            <img :src="secondImageURL" width="24px" height="24px" alt="">
            <a :href="HTMLAddress" class="latest-projects-card-font-first-line">{{ url }}</a>
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
                portrait: undefined,
                imageURL: new URL(`/public/${this.image}`, import.meta.url),
                secondImageURL: new URL(`/public/${this.secondImage}`, import.meta.url),
            }
        },
        beforeMount() {
            if (window.innerHeight > window.innerWidth) {
                this.portrait = true
            } else {
                this.portrait = false
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
    .wrapper-inside {
        display: flex; 
        flex-direction: row; 
        column-gap: 16px;
    }
    .wrapper-inside-second {
        display: flex; 
        flex-direction: column; 
        row-gap: 4px; 
        width: 230px;
    }
    .wrapper-inside-third {
            display: flex; 
            flex-direction: row; 
            column-gap: 12px;
    }
    @media (orientation: portrait) {
        .latest-project-card-wrapper {
            display: flex; 
            flex-direction: column; 
            width: 85vw; 
            background-color: var(--gray-lightest-2, #F7F9FC);            
            padding: 24px;
            box-sizing: border-box;
        }
        .latests-project-font-last-line {
            padding-bottom: 1vh;
        }
    }
    @media (orientation: landscape) {
        .latest-project-card-wrapper {
            display: flex; 
            flex-direction: column; 
            width: 343px; 
            background-color: var(--gray-lightest-2, #F7F9FC);       
            padding: 24px;
            box-sizing: border-box;
        }
    }
</style>