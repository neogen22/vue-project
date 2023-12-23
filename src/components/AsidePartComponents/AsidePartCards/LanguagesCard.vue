<template>
    <div class="wrapper" :style="{paddingBottom: paddingBottom}">
        <img :src="imageURL" alt="">
        <div class="wrapper-inside">
            <span class="language">{{ language }}</span>
            <span class="skill">{{ level }}</span>
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            language: {
                type: String,
                required: true,
            },
            level: {
                type: String,
                required: true,
            },
            image: {
                type: String,
                required: true,
            },
            paddingBottom: {
                type: String,
                default: "28px",
            }
        },
        data() {
            return {
                imageURL: new URL(`/public/${this.image}`, import.meta.url)
            }
        },
    }
</script>

<style scoped>
    img {
        height: 24px;
        width: 32px;
        border-radius: 4px;
    } 
    .language {        
        font-family: 'DM Sans', sans-serif;
        color: var(--Gray-Dark, #47516B);
        font-size: 14.118px;
        font-style: normal;
        font-weight: 500;
        line-height: 18.152px;
    }
    .skill {
        font-family: 'DM Sans', sans-serif;
        color: var(--Gray-Default, #79819A);
        font-size: 12.101px;
        font-style: normal;
        font-weight: 400;
        line-height: 16.135px;
        letter-spacing: 0.121px; 
    }
    .wrapper {
        display: flex;
        flex-direction: row;
        column-gap: 16.13px;
        padding-bottom: 20.17px;
    }
    
    .wrapper-inside {
        display: flex; 
        flex-direction: column; 
        row-gap: 4px; 
        margin-top: -3px; 
        line-height: 8px;
    }
</style>