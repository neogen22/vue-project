<template>
    <div class="languages-card-wrapper">
        <img :src="imageURL" alt="">
        <div class="languages-card-wrapper-inside">
            <span class="languages-card-language">{{ language }}</span>
            <span class="languages-card-skill">{{ level }}</span>
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
    .languages-card-language {        
        font-family: 'DM Sans', sans-serif;
        color: var(--gray-dark, #47516B);
        font-size: 14px;
        font-style: normal;
        font-weight: 500;
        line-height: 1.29;
    }
    .languages-card-skill {
        font-family: 'DM Sans', sans-serif;
        color: var(--gray-default, #79819A);
        font-size: 12px;
        font-style: normal;
        font-weight: 400;
        line-height: 1.33;
    }
    .languages-card-wrapper {
        display: flex;
        flex-direction: row;
        column-gap: 16px;
    }
    .languages-card-wrapper-inside {
        display: flex; 
        flex-direction: column; 
        row-gap: 4px; 
        margin-top: -3px; 
        line-height: 8px;
    }
</style>