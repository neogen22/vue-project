<template>
    <h1 class="header">{{ asideCardHeader }}</h1>
</template>

<script>
export default {
    props: {
        asideCardHeader: {
            type: String,
            required: true
        }
    }
}
</script>

<style>
    .header {
        color: var(--gray-default, #79819A);
        font-family: 'DM Sans', sans-serif;
        font-size: 12px;
        font-style: normal;
        font-weight: 400;
        line-height: 1.33;
        padding-bottom: 20px;
        box-sizing: content-box;
    } 
</style>