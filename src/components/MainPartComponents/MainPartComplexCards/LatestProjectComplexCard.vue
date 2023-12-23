<template>
    <div class="wrapper">
        <LatestProjectsCard
            first="Alexa Dev Community Landing Page"
            last="Web UI design for alexa developers comunity"
            url="https//figma.com"
            image="FigmaLogo.svg"
            secondImage="FigmaSmallIcon.svg"
            radius="5px 0px 0px 5px"
        />
        <LatestProjectsCard
            first="Portfolio Webpage"
            last="Personal Portfolio webpage with resume and blog"
            url="https://anuragyadav365.github.io"
            image="PortfolioLogo.svg"
            secondImage="anura.svg"
            paddingTopElement="20px"
            radius="0px 5px 5px 0px"
        />
    </div>    
</template>

<script>
import LatestProjectsCard from '../MainPartCards/LatestProjectsCard.vue'
export default {
    components: {
        LatestProjectsCard
    },
}
</script>

<style scoped>
    .wrapper {
        display: flex; 
        flex-direction: row; 
        width: 698px; 
        column-gap: 12px; 
        padding-bottom: 48.4px;
    }
</style>