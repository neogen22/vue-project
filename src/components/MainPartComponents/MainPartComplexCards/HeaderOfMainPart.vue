<template>
    <div class="header-of-main-part" :id="header">{{ header }}</div>
</template>

<script>
    export default {
        props: {
            header: {
                type: String,
                required: true,
            },
        }
    };
</script>

<style scoped>
    @media screen and (min-width: 450px) {
        .header-of-main-part {
            font-family: 'Outfit', sans-serif;
            color: var(--gray-darker, #2E2E48);
            font-size: 24px;
            font-style: normal;
            font-weight: 500;
            line-height: 32px;
            padding-bottom: 32px;
            width: 250px
        }
    }
    @media screen and (max-width: 450px) {
        .header-of-main-part {
            font-family: 'Outfit', sans-serif;
            color: var(--gray-darker, #2E2E48);
            font-size: 24px;
            font-style: normal;
            font-weight: 500;
            line-height: 32px;
            padding-bottom: 3vh;
            padding-left: 5vw;
            width: 250px
        }
    }
</style>