<template>    
    <div class="education-card">
        <div class="education-card-header">
            <img :src="imageURL" alt=""/> 
            <div class="education-font-header" :style="{textWrap: wrap}">{{ university }}</div>
        </div>
        <div class="education-card-footer">
            <div class="science-degree">{{ scienceDegree }}</div>
            <div>{{ years }}</div>
            <div><span>Percentage</span>{{ percentage }}</div>
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            university: {
                type: String,
                required: true
            },
            scienceDegree: {
                type: String,
                required: true
            },        
            years: {
                type: String,
                required: true
            },
            percentage: {
                type: String,
                required: true
            },
            image: {
                type: String,
                required: true
            },
            wrap: {
                type: String,
                default: 'wrap',
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
    .education-card {
        display: flex;
        flex-direction: column;
        row-gap: 8px;
        padding: 16px 24px;
        background-color: rgba(247, 249, 252, 1);
        box-sizing: border-box;
    }
    .education-card-header {
        display: flex;
        flex-direction: row;
        width: 179px;
        align-self: center;
        height: 49px;
        column-gap: 16px;
        padding-bottom: 3px;
        box-sizing: border-box;
    }
    .education-card-footer {
        display: flex;
        flex-direction: column;
        row-gap: 2px;
        width: 179px;
        height: 70px;
        box-sizing: border-box;
        align-self: center;
    }
    .science-degree {
        width: 150px
    }
    img {
        width: 38px;
        height: 46px;
    }
    .education-font-header {
        font-family: 'DM Sans', sans-serif;
        color: var(--gray-darker, #2E2E48);
        font-size: 12px;
        font-style: normal;
        font-weight: 500;
        line-height: 16px;
        width: 130px
    }
    .education-card-footer div:first-child {
        font-family: 'DM Sans', sans-serif;
        color: var(--gray-darker, #2E2E48);
        font-size: 14px;
        font-style: normal;
        font-weight: 500;
        line-height: 18px;
    }
    .education-card-footer div:nth-child(2) {
        font-family: 'DM Sans', sans-serif;
        color: var(--gray-default, #79819A);
        font-size: 10px;
        font-style: normal;
        font-weight: 400;
        margin-top: 0;
    }
    .education-card-footer div:last-child {
        font-family: 'DM Sans', sans-serif;
        color: var(--gray-default, #79819A);
        font-size: 12px;
        font-style: normal;
        font-weight: 400;
        margin-top: -7px;
    }
    .education-card-footer div:last-child span {
        font-family: 'DM Sans', sans-serif;
        color: var(--iris-100, #5D5FEF);
        font-size: 12px;
        font-style: normal;
        font-weight: 400;
        line-height: 2;
    }
</style>