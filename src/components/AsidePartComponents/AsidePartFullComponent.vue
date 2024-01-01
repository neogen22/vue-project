<template>
    <div class='aside-part-full-component'>        
        <AsidePartHeader/>
        <hr class="aside-part-full-component-first-hr">
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
    import AsidePartHeader from './AsidePartHeader.vue'
    export default {
        components: {
            ContactsComplexCard,
            SocialComplexCard,
            LanguageComplexCard,
            HobbiesAndInterestsComplexCard,            
            AsidePartHeader,
        },
    }
</script>

<style scoped>
    @media (orientation: portrait) {
        hr {
            border: none; 
            color: rgba(226, 230, 238, 1); 
            background-color: rgba(226, 230, 238, 1); 
            height: 1px;
            width: 83vw;
            margin-bottom: 3vh;
        }
        .aside-part-full-component {
            width: 85vw;
            background-color: rgb(247, 249, 252);
            padding: 1vw;            
        }
        .aside-part-full-component-first-hr {
            margin-top: 1vh;
        }
    }
    @media (orientation: landscape) {
        hr {
            border: none; 
            color: rgba(226, 230, 238, 1); 
            background-color: rgba(226, 230, 238, 1); 
            height: 1px;
            width: 266px;
            margin-bottom: 32px;
        }
        .aside-part-full-component {
            width: 363px; 
            height: 1698px; 
            background-color: rgb(247, 249, 252); 
            padding-left: 48px; 
            padding-right: 48px
        }        
        .aside-part-full-component-first-hr {
            margin-top: 4px;
        }
    }    
</style>