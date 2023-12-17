<template>
    <link href="https://fonts.googleapis.com/css2?family=DM+Sans:opsz,wght@9..40,400;9..40,500&display=swap" rel="stylesheet">
    <div class="wrapper">
        <div class="wrapper-inside-header">Hobbies & Interests</div>
        <HobbiesAndInterestsCard 
        name="Gaming" 
        image="Play.svg"
        />
        <HobbiesAndInterestsCard 
        name="Traveling" 
        image="Earth.svg"
        />
        <HobbiesAndInterestsCard 
        name="Sketching/Graffitti" 
        image="Brush.svg"
        />
        <HobbiesAndInterestsCard 
        name="Blogging" 
        image="Blogging.svg"
        />
    </div>    
</template>

<script>
    import HobbiesAndInterestsCard from '../FirstPageCards/HobbiesAndInterestsCard.vue'
    export default {
        components: {
            HobbiesAndInterestsCard
        }
    }
</script>

<style scoped>
    .wrapper {
        display: flex;
        flex-direction: column;
        row-gap: 16.13px;
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