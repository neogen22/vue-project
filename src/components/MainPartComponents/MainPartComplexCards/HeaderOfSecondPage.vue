<template>    
    <div class="header">{{ header }}</div>
</template>

<script>
    export default {
        props: {
            header: {
                type: String,
            }
        }
    };
</script>

<style scoped>
    @media (orientation: portrait) {
        .header {
            font-family: 'Outfit', sans-serif;
            color: var(--gray-darker, #2E2E48);
            font-size: 24px;
            font-style: normal;
            font-weight: 500;
            line-height: 32px;
            padding-bottom: 3vh;
            width: 85vw;
            padding-left: 5vw;
        }
    }
    @media (orientation: landscape) {
        .header {
            font-family: 'Outfit', sans-serif;
            color: var(--gray-darker, #2E2E48);
            font-size: 24px;
            font-style: normal;
            font-weight: 500;
            line-height: 32px;
            padding-bottom: 32px
        }
    }
</style>