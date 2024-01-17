<template>    
    <div class="language-complex-card-wrapper">
        <div>
            <AsidePartCardHeader 
                asideCardHeader="Languages"
            />
        </div>
        <div v-for="item in languageCardsArray" :key="item.id">
            <LanguagesCard 
                :language="item.language" 
                :level="item.level" 
                :image="item.image"
            />
        </div>
    </div>
</template>

<script>
    import LanguagesCard from '../AsidePartCards/LanguagesCard.vue'
    import AsidePartCardHeader from '../AsidePartCards/AsidePartCardHeader.vue'
    export default {
        components: {
            LanguagesCard,
            AsidePartCardHeader
        },
        data() {
            return {
                languageCardsArray:[
                    {
                        language:"Hindi",
                        level:"Native",
                        image:"India.svg",
                    },
                    {
                        language:"English", 
                        level:"Professional working",
                        image:"England.svg",
                    },
                    {
                        language:"Spanish", 
                        level:"Elementary", 
                        image:"Wikipedia-Flags-ES-Spain-Flag.svg",
                    }
                ]
            }
        },
        beforeMount() {
            for (let i = 0; i < this.languageCardsArray.length; i += 1) {
                this.languageCardsArray.id = `${i}${this.languageCardsArray[i].language}`
            }
        }
    }
</script>

<style scoped>
    @media screen and (max-width: 1190px) {
        .language-complex-card-wrapper > div {
            padding-bottom: 25px;
        }
        .language-complex-card-wrapper > div:last-child {
            padding-bottom: 22px;
        }
    }
    @media screen and (min-width: 1190px) {
        .language-complex-card-wrapper>div {
            padding-bottom: 20px
        }
        .language-complex-card-wrapper > div:last-child {
            padding-bottom: 32px
        }
    }
    @media screen and (min-width: 650px) and (max-width: 800px) {
        .language-complex-card-wrapper {
            display: grid;
            grid-template-columns: 260px 260px;
        }
        .language-complex-card-wrapper div:first-child {
            grid-column: span 2;
            justify-self: center;
        }
    }
    @media screen and (min-width: 500px) and (max-width: 650px) {
        .language-complex-card-wrapper {
            display: grid;
            grid-template-columns: 200px 200px;
        }
        .language-complex-card-wrapper div:first-child {
            grid-column: span 2;
            justify-self: center;
        }
    }
</style>