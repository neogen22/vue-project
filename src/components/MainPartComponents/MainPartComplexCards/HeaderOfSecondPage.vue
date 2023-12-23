<script>
    export default {
        props: {
            header: {
                type: String,
            }
        }
    };
</script>

<template>
    <link href="https://fonts.googleapis.com/css2?family=Outfit:wght@400;500&display=swap" rel="stylesheet"> 
    <div class="header">{{ header }}</div>
</template>

<style scoped>
    .header {
        font-family: 'Outfit', sans-serif;
        color: var(--Gray-Darker, #2E2E48);        
        font-size: 24.202px;
        font-style: normal;
        font-weight: 500;
        line-height: 32.269px;
        letter-spacing: 0.242px; 
        padding-bottom: 32.27px
    }
</style>