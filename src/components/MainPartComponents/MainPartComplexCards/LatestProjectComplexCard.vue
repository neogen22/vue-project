<template>
    <div class="latest-project-complex-card-wrapper" ref="latestProjectRef">
        <div v-for="item in latestProjectsCardArray" :key="item">
            <LatestProjectsCard
                :first="item.first"
                :last="item.last"
                :url="item.url"
                :image="item.image"
                :secondImage="item.secondImage"
                :paddingTopElement="item.paddingTopElement"
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
            reacted: 0,
            firstElement: '0px 0px 0px 0px',
            secondElement: '0px 0px 0px 0px',
            lastElement: '0px 0px 0px 0px',
            secondLastElement: '0px 0px 0px 0px',
            width: undefined,
            grid: {
                column: 'span 1'
            },
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
                },
            ],            
        }
    },
    methods: {
        changeAngle() {
            const lengthOfLatestProjectCardArray = document.querySelectorAll('.latest-project-card ').length
            if (this.width >= 1190) {
                if (lengthOfLatestProjectCardArray === 1) {
                    this.lastElement = "20px 20px 20px 20px"
                }
                if (lengthOfLatestProjectCardArray === 2) {
                    this.secondLastElement = "20px 0px 0px 20px"
                    this.lastElement = "0px 20px 20px 0px"
                }
                if (lengthOfLatestProjectCardArray > 2 && lengthOfLatestProjectCardArray % 2 === 0) {
                    this.firstElement = '20px 0px 0px 0px'
                    this.secondElement = '0px 20px 0px 0px'
                    this.lastElement = '0px 0px 20px 0px'
                    this.secondLastElement = '0px 0px 0px 20px'
                }
                if (lengthOfLatestProjectCardArray > 2 && lengthOfLatestProjectCardArray % 2 !== 0) {
                    this.firstElement = '20px 0px 0px 0px'
                    this.secondElement = '0px 20px 0px 0px'
                    this.lastElement = '0px 0px 20px 20px'                    
                    this.grid.column = 'span 2'
                }
            }
            if (this.width < 1190) {
                if (this.latestProjectsCardArray.length === 1) {
                    this.lastElement = "20px 20px 20px 20px"
                }
                if (this.latestProjectsCardArray.length > 1) {
                    this.firstElement = "20px 20px 0px 0px"
                    this.lastElement = "0px 0px 20px 20px"
                }
            }
        }
    },
    watch: {
        width() {
            this.changeAngle()
        },
        reacted() {
            this.changeAngle()
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
    mounted() {
        this.changeAngle()
        const latestProjectsCardArrayObserver = new MutationObserver(() => {
            this.reacted += 1
        })
        latestProjectsCardArrayObserver.observe(this.$refs.latestProjectRef, {childList: true})
    },
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
        .latest-project-complex-card-wrapper div:first-child > div {
            border-radius: v-bind('firstElement');
        }
        .latest-project-complex-card-wrapper div:nth-child(2) > div {
            border-radius: v-bind('secondElement');
        }
        .latest-project-complex-card-wrapper div:last-child > div {
            border-radius: v-bind('lastElement');
        }
        .latest-project-complex-card-wrapper div:nth-last-child(2) > div {
            border-radius: v-bind('secondLastElement');
        }
        .latest-project-complex-card-wrapper div:last-child {
            grid-column: v-bind('grid.column');
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
        .latest-project-complex-card-wrapper div:first-child > div {
            border-radius: v-bind('firstElement');
        }
        .latest-project-complex-card-wrapper div:last-child > div {
            border-radius: v-bind('lastElement');
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
        .latest-project-complex-card-wrapper div:first-child > div {
            border-radius: v-bind('firstElement');
        }
        .latest-project-complex-card-wrapper div:last-child > div {
            border-radius: v-bind('lastElement');
        }
    }
</style>