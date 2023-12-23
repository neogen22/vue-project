<template>    
    <div class="wrapper">        
        <AsidePartCardHeader 
        asideCardHeader="Languages"                
        />
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
        paddingBottom="32.27px"
        />
    </div>
</template>

<script>
    import LanguagesCard from '../AsidePartCards/LanguagesCard.vue'
    import AsidePartCardHeader from '../AsidePartCards/AsidePartCardHeader.vue'
    export default {
        components: {
            LanguagesCard,
            AsidePartCardHeader
        }
    }
</script>

<style scoped>
</style>