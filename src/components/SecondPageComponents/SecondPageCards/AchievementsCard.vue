<template>
    <link href="https://fonts.googleapis.com/css2?family=DM+Sans:opsz,wght@9..40,400;9..40,500&display=swap" rel="stylesheet"> 
    <div class="wrapper" ref="forWrapperLine">
        <div style="display: flex; flex-direction: column;">
            <img src="..\SecondPageIcons\icon.svg" class="achievements-icon-img" alt="" ref="forWrapperLineCircle">
            <svg v-if="!firstLine" :height="wrapperLine" width="4" style='padding-left: 3px' class="line">
                <line x1="0" y1="0" x2="0" :y2="wrapperLine" style="stroke:rgb(226, 230, 238);stroke-width:1" />
            </svg>
            <svg v-else :height="wrapperLine" width="4" style='padding-left: 3px' class="line">
                <line x1="0" y1="10" x2="0" :y2="wrapperLine" style="stroke:rgb(226, 230, 238);stroke-width:1" />
            </svg>
        </div>
        <div class="company" :style="{paddingBottom: pad}">
            <div style="display: flex; flex-direction: column; row-gap:8px;">
                <div style="display: flex; flex-direction: row; column-gap: 4px;">
                    <div class="dates" v-if="dates==='Present'" style="background: var(--Primary-Lighter, #EFE2F9); border-radius: 4.034px; color: var(--Primary-Default, #9251F7); padding: 0px 4.034px;">{{dates}}</div>
                    <div class="dates" v-else>{{dates}}</div>
                    <div style="display: flex; flex-direction: row; column-gap: 4px;">
                        <img src="..\SecondPageIcons\location.svg" class="achievements-location-img" alt="">
                        <div class="status">{{ status }}</div>                        
                    </div>
                </div>
                <div style="display: flex; flex-direction: row; column-gap: 8px; width:242px; margin-left: 7px">
                    <img :src="getImageUrl()" class="achievements-company-logo-img" alt="" :style="{width: widthSVG, height: heightSVG}">
                    <div style="display: flex; flex-direction: column; row-gap:4px">            
                        <div class="achievements-contributor-font">{{ contributor }}</div>
                        <div class="achievements-company-font">{{ company }}</div>
                    </div>
                </div>        
            </div>
            <div class="achievements-description-font">{{ text }}</div>
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            dates: String,
            contributor: String,
            company: String,
            text: String,
            status: String,
            image: String,
            line: {
                type: String,
                default: 'achievements-line-img'
            },
            pad: {
                type: String,
                default: '16.13px'
            },
            firstLine: {
                type: Boolean,
                default: false,
            },
            widthSVG: String,
            heightSVG: String,
        },
        data() {
            return {
                wrapperLine: 0,
            }
        },
        methods: {
            getImageUrl() {
                return new URL(`../SecondPageIcons/${this.image}`, import.meta.url)
            }
        },
        mounted() {
            this.wrapperLine = this.$refs.forWrapperLine.clientHeight 
        }        
    }
</script>

<style scoped>
    img {
        align-self: center;
    }
    .line {
        position: absolute;
        z-index: -1;
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
        color: var(--Gray-Dark, #47516B);
        font-size: 10.084px;
        font-style: normal;
        font-weight: 400;
        line-height: normal;
        letter-spacing: 0.101px; 
    }
    .status {        
        font-family: 'DM Sans', sans-serif;
        color: var(--Gray-Default, #79819A);
        font-size: 10.084px;
        font-style: normal;
        font-weight: 400;
        line-height: normal;
        letter-spacing: 0.101px; 
    }
    .achievements-company-font {        
        font-family: 'DM Sans', sans-serif;
        color: var(--Gray-Darker, #2E2E48);
        font-size: 14.118px;
        font-style: normal;
        font-weight: 500;
        line-height: 18.152px;
    }
    .achievements-description-font {            
        font-family: 'DM Sans', sans-serif;
        color: var(--Gray-Default, #79819A);
        font-size: 12.101px;
        font-style: normal;
        font-weight: 400;
        line-height: 13px;
        letter-spacing: 0.121px;  
    }
    .achievements-contributor-font {        
        font-family: 'DM Sans', sans-serif;
        color: var(--Gray-Default, #79819A);
        font-size: 12.101px;
        font-style: normal;
        font-weight: 400;
        line-height: 16.135px;
        letter-spacing: 0.121px; 
        width: 185.5px
    }
    .achievements-icon-img {
        padding-top: 9px;
        padding-left: 1px;
    }   
    .company {
        display: flex; 
        flex-direction: row; 
        column-gap: 4px; 
    }
    .wrapper {
        display: flex; 
        flex-direction: row; 
        column-gap: 16.13px; 
        width: 657.5px; 
        box-sizing: border-box;
    }    
</style>