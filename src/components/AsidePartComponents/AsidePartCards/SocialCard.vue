<template>
    <div class="wrapper" :style="{paddingBottom: paddingBottom}">
        <img :src="imageURL" alt="">
        <div class="wrapper-inside">
            <span class="social-media-name">{{ name }}</span>
            <a :href="HTMLAddress"><span class="social-media-address">{{ address }}</span></a>
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
            paddingBottom: {
                type: String,
                default: "22px",
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
	    font-size: 100%;
	    font: inherit;
	    vertical-align: baseline;
        line-height: 0px;
        
    }
    img {
        width: 32px;
        height: 32px;
        align-self: center;
    }
    .social-media-name {
        font-family: 'DM Sans', sans-serif;        
        color: var(--Gray-Default, #79819A);        
        font-size: 12.101px;
        font-style: normal;
        font-weight: 400;
        line-height: 1.33;
        letter-spacing: 0.121px;
    }
    .social-media-address {
        font-family: 'DM Sans', sans-serif;
        color: var(--Gray-Dark, #47516B);
        font-size: 14.118px;
        font-style: normal;
        font-weight: 500;
        line-height: 1.29;
        text-decoration-line: underline; 
    }
    .wrapper {
        display: flex;
        flex-direction: row;
        column-gap: 16.13px;
        padding-bottom: 20.17px
    }
    .wrapper-inside {
        display: flex;
        flex-direction: column;
        row-gap: 4.03px;
    }
</style>