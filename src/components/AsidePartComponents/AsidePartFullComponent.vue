<template>
    <div class='aside-part-full-component' v-if="width > 800 || width < 450">
        <AsidePartHeader/>
        <hr class="aside-part-full-component-first-hr">
        <ContactsComplexCard/>
        <hr>
        <SocialComplexCard/>
        <hr>
        <LanguageComplexCard/>
        <HobbiesAndInterestsComplexCard/>
    </div>
    <div class='alternative' v-else>
        <AsidePartHeader/>
        <div class="aside-part-full-component-medium">
            <ContactsComplexCard/>
        </div>
            <SocialComplexCard/>
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
        data() {
            return {
                width: undefined,
            }
        },
        created() {
            this.width = window.innerWidth
            window.addEventListener('resize', () => {
                this.width = window.innerWidth
            })
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
        @media screen and (max-width:450px)  {
            .aside-part-full-component {
                height: 1460px;
            }
        }
        @media screen and (max-width: 800px) and (min-width: 450px) {
            .aside-part-full-component-medium {
                display: grid;
                grid-template-columns: 1fr 1fr;
            }
            .alternative {
                background-color: rgb(247, 249, 252);
            }
        }
</style>