<template>
    <div class="wrapper">
        <img :src="imageURL" alt="">
        <span class="font">{{ name }}</span>
    </div>
</template>

<script>
    export default{
        props: {
            name: {
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
        width: 34px;
        height: 34px;
    }
    .font {        
        font-family: 'DM Sans', sans-serif;
        color: var(--gray-dark, #47516B);
        font-size: 14px;
        font-style: normal;
        font-weight: 500;
        line-height: 1.29;
        align-self: center;
    }
    .wrapper {
        display: flex; 
        column-gap: 16px;
        padding-bottom: 16px;
    }
</style>