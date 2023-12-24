<template>
    <div class="wrapper" :style="{paddingBottom: paddingBottom}">
        <img :src="imageURL" alt="">
        <div class="wrapper-inside">
            <span class="type-of-address">{{ type }}</span>
            <span class="address" :style="{textDecoration: decoration}" v-if="type==='Email'"><a href="mailto">{{ address }}</a></span>
            <span class="address" :style="{textDecoration: decoration}" v-else-if="type==='Phone'"><a href="tel">{{ address }}</a></span>
            <span class="address" :style="{textDecoration: decoration}" v-else-if="type==='Website'"><a href="https://anuragyadav365.github.io/portfolio.html">{{ address }}</a></span>
            <span class="address" :style="{textDecoration: decoration}" v-else>{{ address }}</span>
        </div>
    </div>
</template>

<script>
export default{
    props: {
        image: {
            type: String,
            required: true,
        },
        type: {
            type: String,
            required: false,
        },
        address: {
            type: String,
            required: true,
        },
        decoration: {
            type: String,
            default: 'none',
        },
        paddingBottom: {
            type: String,
            default: "31px",
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
        text-decoration: none;
        padding: 0;
        margin: 0;
        color: var(--gray-dark);
        font-family: 'DM Sans', sans-serif;
        font-size: 14.118px;
        font-style: normal;
        font-weight: 500;
        line-height: 1.29;
    }
    img {
        align-self: center;
        width: 32px;
        height: 32px;
    }
    .address {
        color: var(--gray-dark);
        font-family: 'DM Sans', sans-serif;
        font-size: 14.118px;
        font-style: normal;
        font-weight: 500;
        line-height: 1.29;
    }
    .type-of-address {
        color: var(--Gray-Default, #79819A); 
        font-family: 'DM Sans', sans-serif;
        font-size: 12.101px;
        font-style: normal;
        font-weight: 400;
        line-height: 1.33;
        letter-spacing: 0.121px; 
    }
    .wrapper {
        display: flex; 
        column-gap: 16.13px;        
    }
    .wrapper-inside {
        display: flex; 
        flex-direction: column; 
        row-gap: 2px; 
        line-height: 8px;
    }
</style>