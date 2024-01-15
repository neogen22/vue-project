<template>    
    <div class="language-complex-card-wrapper" v-if="width > 800 || width < 450">
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
    <div v-else>
        <div class="header">
            <AsidePartCardHeader
                asideCardHeader="Languages"
            />
        </div>
        <div class="language-complex-card-wrapper-alternative">
            <div v-for="item in languageCardsArray" :key="item.id">
                <LanguagesCard 
                    :language="item.language" 
                    :level="item.level" 
                    :image="item.image"
                />
            </div>
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
                width: undefined,
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
        created() {
            this.width = window.innerWidth
            window.addEventListener('resize', () => {
                this.width = window.innerWidth
            })
        },
    }
</script>

<style scoped>
    @media screen and (max-width: 1190px) {
        .language-complex-card-wrapper>div {
            padding-bottom: 25px;
        }
        .language-complex-card-wrapper>div:last-child {
            padding-bottom: 22px;
        }
    }
    @media screen and (min-width: 1190px) {
        .language-complex-card-wrapper>div {
            padding-bottom: 20px
        }
        .language-complex-card-wrapper>div:last-child {
            padding-bottom: 32px
        }
    }
    @media screen and (max-width: 800px) and (min-width: 450px) {
        .social-complex-card-wrapper {
            padding-top: 10px;
            display: grid;
            grid-template-columns: 260px 260px;
        }
        .header {
            margin-left: 240px;            
        }
        .language-complex-card-wrapper-alternative {
            padding-top: 10px;
            display: grid;
            grid-template-columns: 190px 190px 190px;
        }        
        .language-complex-card-wrapper-alternative div {
            padding-top: 10px;
            align-self: center;
        }
    }
</style>