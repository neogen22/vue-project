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
    import ContactsComplexCard from './FirstPageComplexCards/ContactsComplexCard.vue';
    import SocialComplexCard from './FirstPageComplexCards/SocialComplexCard.vue';
    import LanguageComplexCard from './FirstPageComplexCards/LanguageComplexCard.vue';
    import HobbiesAndInterestsComplexCard from './FirstPageComplexCards/HobbiesAndInterestsComplexCard.vue';    
    import FirstPageHeader from './FirstPageHeader.vue'
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
        margin-top: 16px;
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