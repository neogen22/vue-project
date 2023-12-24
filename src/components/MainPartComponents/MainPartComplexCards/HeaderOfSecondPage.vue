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
        color: var(--gray-darker, #2E2E48);
        font-size: 24px;
        font-style: normal;
        font-weight: 500;
        line-height: 32px;
        padding-bottom: 32px
    }
</style>