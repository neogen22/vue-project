<template>    
    <div class="achievements-card-wrapper">
        <div class="achievements-card-wrapper-dot-and-line">
            <img src="/public/icon.svg" class="achievements-icon-img" alt="">
        </div>
        <div class="achievements-card-wrapper-date-company-and-description-grid">
            <div class>
                <div class="achievements-card-wrapper-date-company-and-description-date-location-grid">
                    <span class="dates dates-present" v-if="dates==='Present'">{{dates}}</span>
                    <span class="dates" v-else>{{dates}}</span>
                    <img src="/public/location.svg" class="achievements-location-img" alt="">
                    <span class="status">{{ status }}</span>
                </div>                
                <div class="achievements-card-wrapper-date-company-and-description-grid-inside">
                    <img :src="imageURL" class="achievements-company-logo-img" alt="" :style="{width: widthSVG, height: heightSVG}">
                    <div class="achievements-card-wrapper-date-company-and-description-grid-inside-inside">
                        <span class="achievements-contributor-font">{{ contributor }}</span> 
                        <span class="achievements-company-font">{{ company }}</span>
                    </div>
                </div>
            </div>    
            <span class="achievements-description-font">{{ text }}</span>            
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            dates: {
                type: String,
                required: true
            },
            contributor: {
                type: String,
                required: true
            },
            company: {
                type: String,
                required: true
            },
            text: {
                type: String,
                required: true
            },
            status: {
                type: String,
                required: true
            },
            image: {
                type: String,
                required: true
            },
            widthSVG: {
                type: String,
                required: true
            },
            heightSVG: {
                type: String,
                required: true
            },
        },
        data() {
            return {
                width: undefined,
                wrapperLine: 0,
                imageURL: new URL(`/public/${this.image}`, import.meta.url),
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
    @media screen and (min-width: 1190px) {
        .achievements-card-wrapper-date-company-and-description-grid {
            display: grid;
            grid-template-columns: 250px auto;
        }
        .achievements-card-wrapper-date-company-and-description-date-location-grid {
            display: flex;
            flex-direction: row; 
            column-gap: 4px;
            margin-left: 5px;
        }
        .achievements-card-wrapper-date-company-and-description-date-location-grid:nth-child(1) {
            align-self: start;
        }
        .achievements-card-wrapper-date-company-and-description-grid-inside-inside {
            display: flex;
            flex-direction: column;
            row-gap: 4px;
        }
        .achievements-card-wrapper-date-company-and-description-grid-inside {
            display: flex;
            flex-direction: row;
            padding-top: 8px
        }
    }
    @media screen and (max-width: 1190px) {
        .achievements-card-wrapper-date-company-and-description-grid {
            display: grid;
            grid-template-rows: auto auto;
        }
        .achievements-card-wrapper-date-company-and-description-date-location-grid {
            display: flex;
            flex-direction: row; 
            column-gap: 4px;
            margin-left: 5px;
        } 
        .achievements-card-wrapper-date-company-and-description-date-location-grid:nth-child(1) {
            align-self: start;
        }
        .achievements-card-wrapper-date-company-and-description-grid-inside-inside {
            display: flex;
            flex-direction: column;
            row-gap: 4px;
        }
        .achievements-card-wrapper-date-company-and-description-grid-inside {
            display: flex;
            flex-direction: row;
            padding-top: 8px
        }
    }
    .achievements-card-wrapper-dot-and-line {
        display: flex; 
        flex-direction: column;
    }    
    .achievements-company-logo-img {
        width: 49px;
        height: 49px;
        border-radius: 5px;
    }
    .achievements-location-img {
        width: 12px;
        height: 12px;
        align-self: center;
    }
    .dates {        
        font-family: 'DM Sans', sans-serif;
        color: var(--gray-dark, #47516B);
        font-size: 10px;
        font-style: normal;
        font-weight: 400;
    }
    .dates-present {
        background: var(--primary-lighter, #EFE2F9);
        border-radius: 4px; 
        color: var(--primary-default, #9251F7);
        padding: 0 4px;
        top: 50%
    }
    .status {        
        font-family: 'DM Sans', sans-serif;
        color: var(--gray-default, #79819A);
        font-size: 10px;
        font-style: normal;
        font-weight: 400;
    }
    .achievements-company-font {
        font-family: 'DM Sans', sans-serif;
        color: var(--gray-darker, #2E2E48);
        font-size: 14px;
        font-style: normal;
        font-weight: 500;
        line-height: 1.29;
    }
    .achievements-contributor-font {
        font-family: 'DM Sans', sans-serif;
        color: var(--gray-default, #79819A);
        font-size: 12px;
        font-style: normal;
        font-weight: 400;
        line-height: 16px;
        width: 186px
    }
    .achievements-icon-img {
        padding-left: 1px;
        padding-top: 5px;
        z-index: 2;        
    }
    @media screen and (min-width: 1190px) {
        .achievements-card-wrapper {
            display: flex; 
            flex-direction: row; 
            column-gap: 16px;
            width: 658px;
            box-sizing: border-box;
        }
        .achievements-description-font {
            font-family: 'DM Sans', sans-serif;
            color: var(--gray-default, #79819A);
            font-size: 12px;
            font-style: normal;
            font-weight: 400;
            line-height: 1.17;
            width: 410px;
        }
        img {
            align-self: center;
        }
        .achievements-company-logo-img {
            width: 49px;
            height: 49px;
            border-radius: 5px;
            margin-right: 10px
        }
    }
    @media screen and (max-width: 1190px) and (min-width: 450px) {
        .achievements-card-wrapper {
            display: flex; 
            flex-direction: row; 
            column-gap: 16px;           
            box-sizing: border-box;
        }
        .achievements-description-font {
            padding-top:6px;
            font-family: 'DM Sans', sans-serif;
            color: var(--gray-default, #79819A);
            font-size: 12px;
            font-style: normal;
            font-weight: 400;
            line-height: 1.17;
            width: 420px;
            text-align: justify;
        }
        img {
            align-self: center;
        }
        .achievements-company-logo-img {
            width: 49px;
            height: 49px;
            border-radius: 5px;
            margin-right: 15px
        }
    }
    
    @media screen and (max-width: 450px) {
        .achievements-card-wrapper {
            display: flex; 
            flex-direction: row; 
            column-gap: 16px;
            box-sizing: border-box;            
        }
        .achievements-description-font {
            font-family: 'DM Sans', sans-serif;
            color: var(--gray-default, #79819A);
            font-size: 12px;
            font-style: normal;
            font-weight: 400;
            line-height: 1.17;
            width: 310px;
            text-align: justify;
        }
        img {
            align-self: center;
        }
        .achievements-company-logo-img {
            width: 49px;
            height: 49px;
            border-radius: 5px;
            margin-right: 15px
        }
    }
    @media screen and (max-width: 950px) {
        .achievements-card-wrapper {
            display: flex; 
            flex-direction: row; 
            column-gap: 16px;
            box-sizing: border-box;
        }
        .achievements-description-font {
            font-family: 'DM Sans', sans-serif;
            color: var(--gray-default, #79819A);
            font-size: 12px;
            font-style: normal;
            font-weight: 400;
            line-height: 1.17;
            width: 310px;
            text-align: justify;
        }
        img {
            align-self: center;
        }
        .achievements-company-logo-img {
            width: 49px;
            height: 49px;
            border-radius: 5px;
            margin-right: 15px
        }
    }
    @media screen and (min-width: 570px) and (max-width: 800px) {
        .achievements-card-wrapper {
            display: flex; 
            flex-direction: row; 
            column-gap: 16px;
            box-sizing: border-box;
        }
        .achievements-description-font {
            font-family: 'DM Sans', sans-serif;
            color: var(--gray-default, #79819A);
            font-size: 12px;
            font-style: normal;
            font-weight: 400;
            line-height: 1.17;
            width: 410px;
            text-align: justify;
        }
        img {
            align-self: center;
        }
        .achievements-company-logo-img {
            width: 49px;
            height: 49px;
            border-radius: 5px;
            margin-right: 15px
        }
    }
</style>