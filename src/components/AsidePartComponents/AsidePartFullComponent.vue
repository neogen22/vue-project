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
            padding-right: 48px;
        }
        .aside-part-full-component-first-hr {
            margin-top: 4px;
        }
        @media screen and (max-width: 1190px)  {
            .aside-part-full-component {
                height: 1650px;
            }
        }
        @media screen and (min-width: 500px) and (max-width: 800px) {
            .aside-part-full-component {
                height: auto;
                width: 650px;
            }
            hr {
                width: auto;
                margin-bottom: 16px;
            }
        }
        @media screen and (max-width:650px)  {
            .aside-part-full-component {
                height: 1120px;
            }
        }
        @media screen and (max-width:500px)  {
            .aside-part-full-component {
                height: 1500px;
            }
        }
</style>