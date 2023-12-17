<template>    
    <div class="wrapper">
        <div class="wrapper-inside-header">Socials</div>
        <SocialCard 
        name="Instagram" 
        address="@anurag.yadav.007" 
        image="InstagramIcon.svg"
        />
        <SocialCard 
        name="GitHub" 
        address="@anuragyadav365" 
        image="GitHubLogo.svg"
        />
        <SocialCard 
        name="Twitter" 
        address="@anurag.yadav.007" 
        image="TwitterLogo.svg"
        />
        <SocialCard 
        name="Linkedin" 
        address="@anuragyadav" 
        image="LinkedinLogo.svg"
        />
    </div>
</template>

<script>
    import SocialCard from '../FirstPageCards/SocialCard.vue'
    export default {
        components: {
            SocialCard
        },
    }
</script>

<style scoped>
    .wrapper {
        display: flex;
        flex-direction: column;
        padding-top: 32.27px;
        row-gap: 20.17px;
    }
    .wrapper-inside-header {
        color: var(--gray-default, #79819A);
        font-family: 'DM Sans', sans-serif;
        font-size: 12.101px;
        font-style: normal;
        font-weight: 400;
        line-height: 16.135px;
        letter-spacing: 0.121px; 
    }
</style>