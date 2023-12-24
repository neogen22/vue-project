<template>
    <div class='page-1'>        
        <FirstPageHeader/>
        <hr class="first-hr">
        <ContactsComplexCard/>
        <hr>
        <SocialComplexCard/>
        <hr>
        <LanguageComplexCard/>
        <HobbiesAndInterestsComplexCard/>        
    </div>
</template>

<script>
    import ContactsComplexCard from './AsidePartComplexCards/ContactsComplexCard.vue';
    import SocialComplexCard from './AsidePartComplexCards/SocialComplexCard.vue';
    import LanguageComplexCard from './AsidePartComplexCards/LanguageComplexCard.vue';
    import HobbiesAndInterestsComplexCard from './AsidePartComplexCards/HobbiesAndInterestsComplexCard.vue';    
    import FirstPageHeader from './AsidePartHeader.vue'
    export default {
        components: {
            ContactsComplexCard,
            SocialComplexCard,
            LanguageComplexCard,
            HobbiesAndInterestsComplexCard,            
            FirstPageHeader,
        },
    }
</script>

<style scoped>    
    hr {
        border: none; 
        color: rgba(226, 230, 238, 1); 
        background-color: rgba(226, 230, 238, 1); 
        height: 1px;
        width: 266px;
        margin-bottom: 32px;
    }
    .first-hr {
        margin-top: 4px;
    }   
    .page-1 {
        width: 363px; 
        height: 1698px; 
        background-color: rgb(247, 249, 252); 
        padding-left: 48px; 
        padding-right: 48px
    }
</style>