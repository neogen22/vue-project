<template>
    <div class="achievements-complex-card-wrapper">
        <div v-for="item in achievementsCardArray" :key="item.id">
            <AchievementsCard
                :dates="item.dates"
                :contributor="item.contributor"
                :company="item.company"
                :status="item.status"
                :text="item.text"
                :image="item.image"
                :widthSVG="item.widthSVG"
                :heightSVG="item.heightSVG"
            />
        </div>
    </div>
</template>

<script>
import AchievementsCard from '../MainPartCards/AchievementsCard.vue';
export default {
    components: {
        AchievementsCard,
    },
    data() {
        return {
            achievementsCardArray: [
                {
                    dates: 'Present',
                    contributor:"Graphic Designer",
                    company:"Alexa Dev Community",
                    status:"Chandigarh",
                    text:"Creatively Designing and Developing web UI for Chandigarh University’s Alexa Developer Community, upcoming big launch of full website.",
                    image:"AlexaLogo.svg",
                    widthSVG:"40px",
                    heightSVG:"40px",
                },
                {
                    dates: 'Oct 2021 - Nov 2021',
                    contributor:"Hacktoberfest Contributor",
                    company:"Github",
                    status:"Online",
                    text:"Contributed 8 PR’s in various open source projects. Great experience and learning alot about working with Github and open-source. Connecting with developers.",
                    image:"GitHubLogo.svg",
                    widthSVG:"40px",
                    heightSVG:"40px",
                },
                {
                    dates: 'Jan 2021 - March 2021',
                    contributor:"Contributor",
                    company:"Winter of Code",
                    status:"Online",
                    text:"Overwhelming to be a part of DSC NSEC project - DSC NSEC Algorithms for Winter of Code 2020. First introduction to Git and Github. How github is used by most of the programmers in order to manage the projects.",
                    image:"WOC-logo 1.svg",
                    widthSVG:"46px",
                    heightSVG:"45px",
                },
                {
                    dates: 'Oct 2020 - Dec 2020',
                    contributor:"30Days of Google Cloud",
                    company:"Google",
                    status:"Online",
                    text:"Hands on practice on Google Cloud Platform - the tool that powers apps like Google Search, Gmail and YouTube. As part of the program had learned the concepts like computing, application development, big data & machine learning using cloud.",
                    image:"Google.png",
                    widthSVG:"41px",
                    heightSVG:"41px",
                },
            ],
        }
    },
    beforeMount() {
        for (let i = 0; i < this.achievementsCardArray.length; i += 1) {
            this.achievementsCardArray[i].id = `${i}${this.achievementsCardArray[i].company}`
        }
    }
}
</script>

<style scoped>
    @media screen and (min-width: 450px) {
        .achievements-complex-card-wrapper > div {
            padding-bottom: 16px;
        }
        .achievements-complex-card-wrapper > div:last-child {
            padding-bottom: 0;
        }
    }
    @media screen and (min-width:0px) and (max-width: 450px) {
        .achievements-complex-card-wrapper > div {
            padding-bottom: 3vh;
        }
        .achievements-complex-card-wrapper > div:last-child {
            padding-bottom: 0;
        }
    }
</style>