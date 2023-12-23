<template>
    <AsidePartCardHeader 
    asideCardHeader="Hobbies & Interests"                
    />
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
</template>

<script>
    import HobbiesAndInterestsCard from '../AsidePartCards/HobbiesAndInterestsCard.vue'
    import AsidePartCardHeader from '../AsidePartCards/AsidePartCardHeader.vue'
    export default {
        components: {
            HobbiesAndInterestsCard,
            AsidePartCardHeader
        }
    }
</script>

<style scoped>   
</style>