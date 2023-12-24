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
            latestProjectsCardArray: [
                {
                    first:"Alexa Dev Community Landing Page",
                    last:"Web UI design for alexa developers comunity",
                    url:"https://www.figma.com/",
                    image:"FigmaLogo.svg",
                    secondImage:"FigmaSmallIcon.svg",
                    paddingTopElement:"0px",
                    radius:"5px 0px 0px 5px",
                    HTMLAddress:"https://www.figma.com",
                },
                {
                    first:"Portfolio Webpage",
                    last:"Personal Portfolio webpage with resume and blog",
                    url:"https://anuragyadav365.github.io",
                    image:"PortfolioLogo.svg",
                    secondImage:"anura.svg",
                    paddingTopElement:"20px",
                    radius:"0px 5px 5px 0px",
                    HTMLAddress:"https://anuragyadav365.github.io",
                }
            ]
        }
    }
}
</script>

<style scoped>
    .latest-project-complex-card-wrapper {
        display: flex; 
        flex-direction: row; 
        width: 698px; 
        gap: 12px;
        padding-bottom: 48px;
        flex-wrap: wrap;
    }
</style>