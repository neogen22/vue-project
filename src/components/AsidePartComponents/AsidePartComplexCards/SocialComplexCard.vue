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
                        HTMLAddress:"https://linkedin.com/",
                    },
                ]
            }
        },
        beforeMount() {
            for (let i = 0; i < this.socialCardsArray.length; i += 1) {
                this.socialCardsArray[i].id = `${i}${this.socialCardsArray[i].HTMLAddress}`
            }
        }
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
    @media screen and (max-width: 800px) and (min-width: 650px) {
        .social-complex-card-wrapper {
            display: grid;
            grid-template-columns: 260px 260px;
        }
        .social-complex-card-wrapper div:first-child {
            grid-column: span 2;
            justify-self: center;
        }
    }
    @media screen and (max-width: 650px) and (min-width: 500px) {
        .social-complex-card-wrapper {
            display: grid;
            grid-template-columns: 200px 200px;
            margin-left: auto;
            margin-right: auto;
        }
        .social-complex-card-wrapper div:first-child {
            grid-column: span 2;
            justify-self: center;
        }
    }
</style>