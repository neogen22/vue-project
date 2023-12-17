<template>
    <link href="https://fonts.googleapis.com/css2?family=DM+Sans:opsz,wght@9..40,400;9..40,500&display=swap" rel="stylesheet">
    <div class="wrapper">
        <div class="wrapper-inside-header">Languages</div>
        <LanguagesCard 
        language="Hindi" 
        level="Native" 
        image="India.svg"
        />
        <LanguagesCard 
        language="English" 
        level="Professional working" 
        image="England.svg"
        />
        <LanguagesCard 
        language="Spanish" 
        level="Elementary" 
        image="Wikipedia-Flags-ES-Spain-Flag.svg"
        />
    </div>
</template>

<script>
    import LanguagesCard from '../FirstPageCards/LanguagesCard.vue'
    export default {
        components: {
            LanguagesCard
        }
    }
</script>

<style scoped>
    .wrapper {
        display: flex;
        flex-direction: column;
        row-gap: 20.17px;
        padding-top: 32.27px;
    }
    .wrapper-inside-header {       
        font-family: 'DM Sans', sans-serif;
        color: var(--Gray-Default, #79819A);
        font-size: 12.101px;
        font-style: normal;
        font-weight: 400;
        line-height: 16.135px;
        letter-spacing: 0.121px; 
    }    
</style>