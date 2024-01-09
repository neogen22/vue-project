<template>
    <div class="social-complex-card-wrapper">
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
    }
</script>

<style scoped>
    @media (orientation: portrait) {
        .social-complex-card-wrapper>div {
            padding-bottom: 3vh
        }
        .social-complex-card-wrapper>div:last-child {
            padding-bottom: 4vh
        }
    }
    @media (orientation: landscape) {
        .social-complex-card-wrapper>div {
            padding-bottom: 20px;
        }
        .social-complex-card-wrapper>div:last-child {
            padding-bottom: 32px;
        }
    }
</style>