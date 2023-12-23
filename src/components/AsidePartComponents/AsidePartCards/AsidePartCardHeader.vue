<template>
    <h1 class="header">{{ asideCardHeader }}</h1>
</template>

<script>
export default {
    props: {
        asideCardHeader: {
            type: String,
            requierd: true
        }
    }
}
</script>

<style>
    .header {
        color: var(--gray-default, #79819A);
        font-family: 'DM Sans', sans-serif;
        font-size: 12.101px;
        font-style: normal;
        font-weight: 400;
        line-height: 16.135px;
        letter-spacing: 0.121px;        
        padding-bottom: 20.17px;
        box-sizing: content-box;
    } 
</style>