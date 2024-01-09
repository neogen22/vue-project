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
            width: undefined,
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
    created() {
        this.width = window.innerWidth
        window.addEventListener('resize', () => {
            this.width = window.innerWidth
        })
    },
    methods: {
        changeAngle() {
            for (let i = 0; i < this.latestProjectsCardArray.length; i += 1) {
                this.latestProjectsCardArray[i].radius = "0px 0px 0px 0px"
            }
            if (this.width > 1189) {
                if (this.latestProjectsCardArray.length === 1) {
                    this.latestProjectsCardArray[0].radius = "10px 10px 10px 10px"
                }
                if (this.latestProjectsCardArray.length === 2) {
                    this.latestProjectsCardArray[0].radius = "10px 0px 0px 10px"
                    this.latestProjectsCardArray[1].radius = "0px 10px 10px 0px"
                }
            }
            if (this.width < 1190) {
                if (this.latestProjectsCardArray.length === 1) {
                    this.latestProjectsCardArray[0].radius = "10px 10px 10px 10px"
                }
                if (this.latestProjectsCardArray.length > 1) {
                    this.latestProjectsCardArray[0].radius = "10px 10px 0px 0px"
                    this.latestProjectsCardArray[this.latestProjectsCardArray.length - 1].radius = "0px 0px 10px 10px"
                }
            }
        }

    },
    watch: {
        width() {
            this.changeAngle()
        }
    }
    
}
</script>

<style scoped>
    @media screen and (min-width: 1190px) {
        .latest-project-complex-card-wrapper {
            display: grid;
            grid-template-columns: 345px 345px;
            column-gap: 8px;
            row-gap: 8px;
            box-sizing: border-box;
            padding-bottom: 48px;
        }
    }
    @media screen and (min-width: 950px) and (max-width: 1190px)  {
        .latest-project-complex-card-wrapper {
            display: grid;
            column-gap: 8px;
            row-gap: 8px;
            box-sizing: border-box;
            padding-bottom: 48px;
        }
    }
    @media screen and (min-width: 300px) and (max-width: 950px)  {
        .latest-project-complex-card-wrapper {
            display: grid;
            column-gap: 8px;
            row-gap: 8px;
            box-sizing: border-box;
            padding-bottom: 5vh;
        }
    }
</style>