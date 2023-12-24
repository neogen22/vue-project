<template>
    <div class="social-complex-card-wrapper">
        <AsidePartCardHeader
        asideCardHeader="Socials"
        />
        <SocialCard 
        name="Instagram" 
        address="@anurag.yadav.007" 
        image="InstagramIcon.svg"
        HTMLAddress="https://www.instagram.com/anurag.yadav.007/"
        :paddingBottom="padding"
        />
        <SocialCard 
        name="GitHub" 
        address="@anuragyadav365" 
        image="GitHubLogo.svg"
        HTMLAddress="https://github.com/AnuragYadav365"
        :paddingBottom="padding"
        />
        <SocialCard 
        name="Twitter" 
        address="@anuragmnp" 
        image="TwitterLogo.svg"
        HTMLAddress="https://twitter.com/anuragmnp"
        :paddingBottom="padding"
        />
        <SocialCard 
        name="Linkedin" 
        address="@anuragyadav" 
        image="LinkedinLogo.svg"
        HTMLAddress="https://twitter.com/anuragmnp"
        />
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
                deviceWidth: 0,
                deviceHeight: 0,
                padding: "31px"
            }
        },
        mounted() {
            this.deviceWidth = window.innerWidth
            this.deviceHeight = window.innerHeight
            if (this.deviceHeight > this.deviceWidth) {
                this.padding = "5%"
            }
        }
    }
</script>

<style scoped>
    @media (orientation: portrait) {
        .social-complex-card-wrapper {
            padding-bottom: 7%
        }
    }
    @media (orientation: landscape) {
        .social-complex-card-wrapper {
            padding-bottom: 32px;
        }
    }
</style>