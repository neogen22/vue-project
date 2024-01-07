<template>
    <div class="latest-project-complex-card-wrapper">
        <div v-for="item in latestProjectsCardArray" :key="item">
            <LatestProjectsCard
                :first="item.first"
                :last="item.last"
                :url="item.url"
                :image="item.image"
                :secondImage="item.secondImage"
                :paddingTopElement="item.paddingTopElement"
                :radius="item.radius"
                :HTMLAddress="item.HTMLAddress"
            />
        </div>
    </div>    
</template>

<script>
import LatestProjectsCard from '../MainPartCards/LatestProjectsCard.vue'
export default {
    components: {
        LatestProjectsCard
    },
    data() {
        return {
            portrait: undefined,
            latestProjectsCardArray: [
                {
                    first:"Alexa Dev Community Landing Page",
                    last:"Web UI design for alexa developers comunity",
                    url:"https://www.figma.com/",
                    image:"FigmaLogo.svg",
                    secondImage:"FigmaSmallIcon.svg",
                    paddingTopElement:"0px",                    
                    HTMLAddress:"https://www.figma.com",
                },
                {
                    first:"Portfolio Webpage",
                    last:"Personal Portfolio webpage with resume and blog",
                    url:"https://anuragyadav365.github.io",
                    image:"PortfolioLogo.svg",
                    secondImage:"anura.svg",
                    paddingTopElement:"20px",
                    HTMLAddress:"https://anuragyadav365.github.io",
                }
            ],
        }
    },
    beforeMount() {
        for (let i = 0; i < this.latestProjectsCardArray.length; i += 1) {
            this.latestProjectsCardArray[i].id = `${i}${this.latestProjectsCardArray[i].url}`
        }
    },
    mounted() {
        if (window.innerHeight > window.innerWidth) {
            this.portrait = true
        }
        if (this.portrait) {
            if (this.latestProjectsCardArray.length === 1) {
                this.latestProjectsCardArray[0].radius = "15px 15px 15px 15px"
            } else {
                this.latestProjectsCardArray[0].radius = "15px 15px 0px 0px"
                this.latestProjectsCardArray[this.latestProjectsCardArray.length - 1].radius = "0px 0px 15px 15px"
            }
        } else {
            if (this.latestProjectsCardArray.length === 1) {
                this.latestProjectsCardArray[0].radius = "5px 5px 5px 5px"
            } else {
                this.latestProjectsCardArray[0].radius = "5px 0px 0px 5px"
                this.latestProjectsCardArray[this.latestProjectsCardArray.length - 1].radius = "0px 5px 5px 0px"
            }
        }
    },
}
</script>

<style scoped>
    @media (orientation: portrait) {
        .latest-project-complex-card-wrapper {
            display: flex; 
            flex-direction: column; 
            width: 85vw; 
            gap: 12px;
            padding-bottom: 3vh;
            flex-wrap: wrap;
        }
    }
    @media (orientation: landscape) {
        .latest-project-complex-card-wrapper {
            display: flex; 
            flex-direction: row; 
            width: 698px; 
            gap: 12px;
            padding-bottom: 48px;
            flex-wrap: wrap;            
    }
}
</style>