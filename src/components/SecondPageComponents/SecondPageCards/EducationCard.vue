<template>
    <link href="https://fonts.googleapis.com/css2?family=DM+Sans:opsz,wght@9..40,400;9..40,500&family=Outfit:wght@400;500&display=swap" rel="stylesheet">
    <div class="education-card" :style="{borderRadius: radius}">
        <div class="education-card-header" >
            <img :src="getImageUrl()" alt=""/> 
            <div class="education-font-header" :style="{textWrap: wrap}">{{ university }}</div>
        </div>
        <div class="education-card-footer">
            <div>{{ scienceDegree }}</div>
            <div>{{ years }}</div>
            <div><span>Percentage</span>{{ percentage }}</div>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        university: String,
        scienceDegree: String,        
        years: String,
        percentage: String,
        radius: String,
        image: String,
        wrap: {
            type: String,
            default: 'wrap',
        },        
    },
    methods: {
        getImageUrl() {
            return new URL(`../SecondPageIcons/${this.image}`, import.meta.url)
        }
    },
}
</script>

<style scoped>
    * {
        box-sizing: border-box;
    }
    img {
        width: 38px;
        height: 46px;
    }
    .education-card {
        display: flex;
        flex-direction: column;
        row-gap: 8.07px;
        padding: 16.13px 24.2px;
        background-color: rgba(247, 249, 252, 1);
        width: 227px;
        height: 159px;
        box-sizing: border-box;
    }
    .education-card-header {
        display: flex;
        flex-direction: row;
        width: 179px;
        height: 49px;
        column-gap: 16.13px;
        padding-bottom: 3px;
        box-sizing: border-box;
    }
    .education-card-footer {
        display: flex;
        flex-direction: column;
        row-gap: 2.02px;
        width: 179px;
        height: 70px;
        box-sizing: border-box;
    }
    .education-card-footer div:first-child {
        font-family: 'DM Sans', sans-serif;
        color: var(--Gray-Darker, #2E2E48);
        font-size: 14.118px;
        font-style: normal;
        font-weight: 500;
        line-height: 18px;
    }
    .education-card-footer div:nth-child(2) {
        font-family: 'DM Sans', sans-serif;
        color: var(--Gray-Default, #79819A);        
        font-size: 10.084px;
        font-style: normal;
        font-weight: 400;        
        letter-spacing: 0.101px; 
        margin-top: 0px;
    }
    .education-card-footer div:last-child {
        font-family: 'DM Sans', sans-serif;
        color: var(--Gray-Default, #79819A);
        font-size: 12.101px;
        font-style: normal;
        font-weight: 400;
        margin-top: -7px;        
        letter-spacing: 0.121px; 
    }
    .education-card-footer div:last-child span {   
        font-family: 'DM Sans', sans-serif;     
        color: var(--Iris-100, #5D5FEF);       
        font-size: 12.101px;
        font-style: normal;
        font-weight: 400;
        line-height: normal;
        letter-spacing: 0.121px; 
    }
    .education-font-header {
        font-family: 'DM Sans', sans-serif;
        color: var(--Gray-Darker, #2E2E48);
        font-size: 12.101px;
        font-style: normal;
        font-weight: 500;
        line-height: 16.135px;
    }
</style>