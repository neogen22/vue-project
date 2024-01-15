<template>
    <div class="social-complex-card-wrapper" v-if="width > 800 || width < 450">
        <div>
            <AsidePartCardHeader
                asideCardHeader="Socials"
            />
        </div>    
        <div v-for="item in socialCardsArray" :key="item.id">
            <SocialCard 
                :name="item.name"
                :address="item.address"
                :image="item.image"
                :HTMLAddress="item.HTMLAddress"
            />
        </div>
    </div>
    <div v-else>
        <div class="header">
            <AsidePartCardHeader
                asideCardHeader="Socials"
            />
        </div>
        <div class="social-complex-card-wrapper-alternative">
            <div v-for="item in socialCardsArray" :key="item.id">
                <SocialCard 
                    :name="item.name"
                    :address="item.address"
                    :image="item.image"
                    :HTMLAddress="item.HTMLAddress"
                />
            </div>
        </div>    
    </div>
</template>

<script>
    import SocialCard from '../AsidePartCards/SocialCard.vue'
    import AsidePartCardHeader from '../AsidePartCards/AsidePartCardHeader.vue'
    export default {
        components: {
            SocialCard,
            AsidePartCardHeader
        },
        data() {
            return {
                width: undefined,
                socialCardsArray: [
                    {
                        name:"Instagram", 
                        address:"@anurag.yadav.007", 
                        image:"InstagramIcon.svg",
                        HTMLAddress:"https://www.instagram.com/anurag.yadav.007/",
                    },
                    {
                        name:"GitHub", 
                        address:"@anuragyadav365", 
                        image:"GitHubLogo.svg",
                        HTMLAddress:"https://github.com/AnuragYadav365",
                    },
                    {
                        name:"Twitter", 
                        address:"@anuragmnp", 
                        image:"TwitterLogo.svg",
                        HTMLAddress:"https://twitter.com/anuragmnp",
                    },
                    {
                        name:"Linkedin", 
                        address:"@anuragyadav",
                        image:"LinkedinLogo.svg",
                        HTMLAddress:"https://twitter.com/anuragmnp",
                    },
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
        .social-complex-card-wrapper>div {
            padding-bottom: 25px;
        }
        .social-complex-card-wrapper>div:last-child {
            padding-bottom: 22px
        }
    }
    @media screen and (min-width: 1190px) {
        .social-complex-card-wrapper>div {
            padding-bottom: 20px;
        }
        .social-complex-card-wrapper>div:last-child {
            padding-bottom: 32px;
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
        .social-complex-card-wrapper-alternative {
            padding-top: 10px;
            display: grid;
            grid-template-columns: 260px 260px;
        }        
        .social-complex-card-wrapper-alternative div {
            padding-bottom: 10px;
        }
    }
</style>