<template>    
    <div class="achievements-card-wrapper">
        <div class="achievements-card-wrapper-dot-and-line">
            <img src="/public/icon.svg" class="achievements-icon-img" alt="">           
        </div>
        <div class="achievements-card-wrapper-date-company-and-description">
            <div class="achievements-card-wrapper-date-company-and-description-inside-wrapper">
                <div class="achievements-card-wrapper-date-company-and-description-date">
                    <span class="dates dates-present" v-if="dates==='Present'">{{dates}}</span>
                    <span class="dates" v-else>{{dates}}</span>
                    <div class="achievements-card-wrapper-date-company-and-description-date-location">
                        <img src="/public/location.svg" class="achievements-location-img" alt="">
                        <span class="status">{{ status }}</span>                        
                    </div>
                </div>
                <div class="achievements-card-wrapper-date-company-and-description-company">
                    <img :src="imageURL" class="achievements-company-logo-img" alt="" :style="{width: widthSVG, height: heightSVG}">
                    <div class="achievements-card-wrapper-date-company-and-description-company-achievements">            
                        <span class="achievements-contributor-font">{{ contributor }}</span>
                        <span class="achievements-company-font">{{ company }}</span>
                        <span class="achievements-description-font" v-if="portrait">{{ text }}</span>
                    </div>
                </div>        
            </div>
            <span class="achievements-description-font" v-if="!portrait" ref="test">{{ text }}</span>
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
                portrait: undefined,
                wrapperLine: 0,
                imageURL: new URL(`/public/${this.image}`, import.meta.url),
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
    .achievements-card-wrapper-date-company-and-description-company-achievements {
        display: flex; 
        flex-direction: column; 
        row-gap:4px
    }
    .achievements-card-wrapper-date-company-and-description-inside-wrapper {
        display: flex; 
        flex-direction: column; 
        row-gap:8px;
    }
    .achievements-card-wrapper-date-company-and-description-date {
        display: flex; 
        flex-direction: row; 
        column-gap: 8px;
    }
    .achievements-card-wrapper-date-company-and-description-date-location {
        display: flex; 
        flex-direction: row; 
        column-gap: 4px;
    }
    .achievements-card-wrapper-date-company-and-description-company {
        display: flex; 
        flex-direction: row; 
        column-gap: 8px; 
        width:242px; 
        margin-left: 7px
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
        line-height: normal;
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
        line-height: normal;
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
        -webkit-padding-before: 9px;
    }
    .achievements-card-wrapper-date-company-and-description {
        display: flex; 
        flex-direction: row; 
        column-gap: 4px; 
    }
    @media (orientation: portrait) {
        .achievements-card-wrapper {
            display: flex; 
            flex-direction: row; 
            column-gap: 16px;
            width: 85vw;
            box-sizing: border-box;
        }
        .achievements-description-font {            
            font-family: 'DM Sans', sans-serif;
            color: var(--gray-default, #79819A);
            font-size: 12px;
            font-style: normal;
            font-weight: 400;
            line-height: 1.17;
            width: 65vw;
            text-align: justify;
        }
        .achievements-icon-img {
            padding-left: 1px;
            -webkit-padding-before: 5px;
        }
    }
    @media (orientation: landscape) {
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
    }

</style>