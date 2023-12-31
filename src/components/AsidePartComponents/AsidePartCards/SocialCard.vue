<template>
    <div class="social-card-wrapper">
        <img :src="imageURL" alt="">
        <div class="social-card-wrapper-inside">
            <span class="social-card-name">{{ name }}</span>
            <a :href="HTMLAddress"><span class="social-card-address">{{ address }}</span></a>
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            name: {
                type: String,
                required: true,
            },
            address: {
                type: String,
                required: true,
            },
            image: {
                type: String,
                required: true,
            },
            HTMLAddress: {
                type: String,
                required: true
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
    a {
        padding: 0;
        margin: 0;
        border: 0;
	    vertical-align: baseline;
        line-height: 0;
    }
    img {
        width: 32px;
        height: 32px;
        align-self: center;
    }
    .social-card-name {
        font-family: 'DM Sans', sans-serif;        
        color: var(--gray-default, #79819A);
        font-size: 12px;
        font-style: normal;
        font-weight: 400;
        line-height: 1.33;
    }
    .social-card-address {
        font-family: 'DM Sans', sans-serif;
        color: var(--gray-dark, #47516B);
        font-size: 14px;
        font-style: normal;
        font-weight: 500;
        line-height: 1.29;
        text-decoration-line: underline; 
    }
    .social-card-wrapper {
        display: flex;
        flex-direction: row;
        column-gap: 16px;
    }
    .social-card-wrapper-inside {
        display: flex;
        flex-direction: column;
        row-gap: 4px;
    }
</style>