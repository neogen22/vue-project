<template>
    <link href="https://fonts.googleapis.com/css2?family=DM+Sans:opsz,wght@9..40,400;9..40,500&display=swap" rel="stylesheet">     
    <div class="wrapper">
        <img :src="getImageUrl()" alt="">
        <div class="wrapper-inside">
            <div class="type-of-address">{{ type }}</div>
            <div class="address" :style="{textDecoration: decoration}" v-if="type==='Email'"><a href="mailto">{{ address }}</a></div>
            <div class="address" :style="{textDecoration: decoration}" v-else-if="type==='Phone'"><a href="tel">{{ address }}</a></div>
            <div class="address" :style="{textDecoration: decoration}" v-else-if="type==='Website'"><a href="url">{{ address }}</a></div>
            <div class="address" :style="{textDecoration: decoration}" v-else>{{ address }}</div>
        </div>
    </div>
</template>

<script>
export default{
    props: {
        image: String,
        type: String,
        address:String,
        decoration: {
            type: String,
            default: 'none',
        },
    },
    methods: {
        getImageUrl() {
            return new URL(`../FirstPageIcons/${this.image}`, import.meta.url)
        }
    }
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
        line-height: 18.152px;
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
        line-height: 18.152px;
    }
    .type-of-address {
        color: var(--Gray-Default, #79819A); 
        font-family: 'DM Sans', sans-serif;
        font-size: 12.101px;
        font-style: normal;
        font-weight: 400;
        line-height: 16.135px;
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