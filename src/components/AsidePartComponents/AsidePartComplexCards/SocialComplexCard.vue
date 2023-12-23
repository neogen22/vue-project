<template>   
    <AsidePartCardHeader
    asideCardHeader="Socials"
    />
    <SocialCard 
    name="Instagram" 
    address="@anurag.yadav.007" 
    image="InstagramIcon.svg"
    HTMLAddress="https://www.instagram.com/anurag.yadav.007/"
    />
    <SocialCard 
    name="GitHub" 
    address="@anuragyadav365" 
    image="GitHubLogo.svg"
    HTMLAddress="https://github.com/AnuragYadav365"
    />
    <SocialCard 
    name="Twitter" 
    address="@anuragmnp" 
    image="TwitterLogo.svg"
    HTMLAddress="https://twitter.com/anuragmnp"
    />
    <SocialCard 
    name="Linkedin" 
    address="@anuragyadav" 
    image="LinkedinLogo.svg"
    HTMLAddress="https://twitter.com/anuragmnp"
    paddingBottom="32.27px"
    />
</template>

<script>
    import SocialCard from '../AsidePartCards/SocialCard.vue'
    import AsidePartCardHeader from '../AsidePartCards/AsidePartCardHeader.vue'
    export default {
        components: {
            SocialCard,
            AsidePartCardHeader
        },
    }
</script>

<style scoped>
    .wrapper-inside-header {
        color: var(--gray-default, #79819A);
        font-family: 'DM Sans', sans-serif;
        font-size: 12.101px;
        font-style: normal;
        font-weight: 400;
        line-height: 16.135px;
        letter-spacing: 0.121px;
        margin-top: 0px;
        margin-bottom: 0px;
    }
</style>