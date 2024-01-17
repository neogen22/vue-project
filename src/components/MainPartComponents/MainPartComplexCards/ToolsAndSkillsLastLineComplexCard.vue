<template>
    <div class="tools-and-skills-last-line-wrapper-grid" ref="toolsLastLineRef">
        <div v-for="item in toolsAndSkillsLastLineCardArray" :key="item.id">
            <ToolsAndSkillsLastLineCard
                :technology="item.technology"
                :technologyFor="item.technologyFor"
                :image="item.image"
                :widthOfSVG="item.widthOfSVG"
                :heightOfSVG="item.heightOfSVG"
            />
        </div>    
    </div>
</template>

<script>
    import ToolsAndSkillsLastLineCard from '../MainPartCards/ToolsAndSkillsLastLineCard.vue';
    export default {
        components: {
            ToolsAndSkillsLastLineCard,
        },
        data() {
            return {
                reacted: 0,
                fiveElementFromTheEnd: "0px 0px 0px 0px 0px",
                fourthElementFromTheEnd: "0px 0px 0px 0px 0px",
                thirdElementFromTheEnd: "0px 0px 0px 0px 0px",
                secondElementFromTheEnd: "0px 0px 0px 0px 0px",
                lastElement: "0px 0px 0px 0px",
                width: undefined,
                grid: {
                    column: 'span 1'
                },
                toolsAndSkillsLastLineCardArray: [
                    {
                        technology:"HTML 5",
                        technologyFor:"Structural Design",
                        image:"HTML5Logo.svg",
                        widthOfSVG:"60px",
                        heightOfSVG:"55px"
                    }, 
                    {
                        technology:"CSS 3",
                        technologyFor:"Style Design",
                        image:"CSS3Logo.svg",
                        widthOfSVG:"63px",
                        heightOfSVG:"66px",
                    },
                    {
                        technology:"Wordpress",
                        technologyFor:"Web development",
                        image:"WordPressLogo.svg",
                        widthOfSVG:"68px",
                        heightOfSVG:"61px",
                    },
                    {
                        technology:"VS Code",
                        technologyFor:"Code editor",
                        image:"VSCodeJPG.png",
                        widthOfSVG:"32px",
                        heightOfSVG:"32px",
                    },
                    {
                        technology:"Notion",
                        technologyFor:"Project managment",
                        image:"NotionLogo.svg",
                        widthOfSVG:"32px",
                        heightOfSVG:"32px",
                    },
                ]
            }
        },
        methods: {
            resetAngles() {
                this.fiveElementFromTheEnd = "0px 0px 0px 0px 0px"
                this.fourthElementFromTheEnd = "0px 0px 0px 0px 0px"
                this.thirdElementFromTheEnd = "0px 0px 0px 0px 0px"
                this.secondElementFromTheEnd = "0px 0px 0px 0px 0px"
                this.lastElement = "0px 0px 0px 0px"
            },
            changeAngle() {
                const lengthOfTheToolsLastLine = document.querySelectorAll('.tool-flex-card-last-line-card').length
                if (this.width >= 1190) {
                    let test = Math.abs(lengthOfTheToolsLastLine % 5 - 5)
                    this.resetAngles()
                    if (test === 4) {
                        this.grid.column = 'span 5'
                        this.lastElement = "0px 0px 20px 20px"
                    }
                    if (test === 3) {
                        this.grid.column = 'span 4'
                        this.lastElement = "0px 0px 20px 0px"
                        this.secondElementFromTheEnd = "0px 0px 0px 20px"
                    }
                    if (test === 2) {
                        this.grid.column = 'span 3'
                        this.lastElement = "0px 0px 20px 0px"
                        this.thirdElementFromTheEnd = "0px 0px 0px 20px"
                    }
                    if (test === 1) {
                        this.grid.column = 'span 2'
                        this.fourthElementFromTheEnd = "0px 0px 0px 20px"
                        this.lastElement = "0px 0px 20px 0px"
                    }
                    if (test === 5) {
                        this.grid.column = 'span 1'
                        this.fiveElementFromTheEnd = '0px 0px 0px 20px'
                        this.lastElement = "0px 0px 20px 0px"
                    }
                }
                if ((this.width >= 950 && this.width < 1190) || (this.width >= 570 && this.width <= 800)) {
                    let test = Math.abs(lengthOfTheToolsLastLine % 3 - 3)
                    this.resetAngles()
                    if (test === 1) {
                        this.grid.column = 'span 2'
                        this.lastElement = "0px 0px 20px 0px"
                        this.secondElementFromTheEnd = "0px 0px 0px 20px"
                    }
                    if (test === 2) {
                        this.grid.column = 'span 3'
                        this.lastElement = "0px 0px 20px 20px"
                    }
                    if (test === 3) {
                        this.grid.column = 'span 1'
                        this.lastElement = "0px 0px 20px 0px"
                        this.thirdElementFromTheEnd = "0px 0px 0px 20px"
                    }
                }
                if (this.width < 570 || this.width > 800 && this.width < 950) {
                    this.resetAngles()
                    if (this.toolsAndSkillsLastLineCardArray.length % 2 === 0) {
                        this.grid.column = 'span 1'
                        this.lastElement = "0px 0px 20px 0px"
                        this.secondElementFromTheEnd = "0px 0px 0px 20px"
                    }
                    if (this.toolsAndSkillsLastLineCardArray.length % 2 !== 0) {
                        this.grid.column = 'span 2'
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
            for (let i = 0; i < this.toolsAndSkillsLastLineCardArray.length; i += 1) {
                this.toolsAndSkillsLastLineCardArray[i].id = `${i}${this.toolsAndSkillsLastLineCardArray[i].technology}`
            }
        },
        created() {
            this.width = window.innerWidth
            window.addEventListener('resize', () => {
                this.width = window.innerWidth
            })
        },
        mounted() {
            const toolsLastLineObserver = new MutationObserver(() => {
                this.reacted += 1
            })
            toolsLastLineObserver.observe(this.$refs.toolsLastLineRef, {childList: true})
        },
    }
</script>

<style scoped>
    @media screen and (min-width: 1190px) {
        .tools-and-skills-last-line-wrapper-grid {
            display: grid;
            grid-template-columns: 133px 133px 133px 133px 133px;
            column-gap: 8px;
            row-gap: 8px;
            box-sizing: border-box;
            width: 700px
        }
        .tools-and-skills-last-line-wrapper-grid div:last-child {
            grid-column: v-bind('grid.column');
        }
        .tools-and-skills-last-line-wrapper-grid div > div {
            border-radius: '0px 0px 0px 0px';
        }
        .tools-and-skills-last-line-wrapper-grid div:nth-last-child(5) > div {
            border-radius: v-bind('fiveElementFromTheEnd')
        }
        .tools-and-skills-last-line-wrapper-grid div:nth-last-child(4) > div {
            border-radius: v-bind('fourthElementFromTheEnd')
        }
        .tools-and-skills-last-line-wrapper-grid div:nth-last-child(3) > div {
            border-radius: v-bind('thirdElementFromTheEnd')
        }
        .tools-and-skills-last-line-wrapper-grid div:nth-last-child(2) > div {
            border-radius: v-bind('secondElementFromTheEnd')
        }
        .tools-and-skills-last-line-wrapper-grid div:last-child > div {
            border-radius: v-bind('lastElement')
        }
    }
    @media screen and (min-width: 950px) and (max-width: 1190px) {
        .tools-and-skills-last-line-wrapper-grid {
            display: grid;
            grid-template-columns: 148px 148px 148px;
            row-gap: 8px;
            column-gap: 9px;
            box-sizing: border-box;
        }
        .tools-and-skills-last-line-wrapper-grid div:last-child {
            grid-column: v-bind('grid.column');
        }
        .tools-and-skills-last-line-wrapper-grid div:nth-last-child(3) > div {
            border-radius: v-bind('thirdElementFromTheEnd')
        }
        .tools-and-skills-last-line-wrapper-grid div:nth-last-child(2) > div {
            border-radius: v-bind('secondElementFromTheEnd')
        }
        .tools-and-skills-last-line-wrapper-grid div:last-child > div {
            border-radius: v-bind('lastElement')
        }
    }
    @media screen and (min-width: 800px) and (max-width: 950px) {
        .tools-and-skills-last-line-wrapper-grid {
            display: grid;
            grid-template-columns: 163px 163px;
            column-gap: 8px;
            row-gap: 8px;
            box-sizing: border-box;
        }
        .tools-and-skills-last-line-wrapper-grid div:last-child {
            grid-column: v-bind('grid.column');
        }
        .tools-and-skills-last-line-wrapper-grid div:nth-last-child(2) > div {
            border-radius: v-bind('secondElementFromTheEnd')
        }
        .tools-and-skills-last-line-wrapper-grid div:last-child > div {
            border-radius: v-bind('lastElement')
        }
    }
    @media screen and (min-width: 570px) and (max-width: 800px) {
        .tools-and-skills-last-line-wrapper-grid {
            display: grid;
            grid-template-columns: 148px 148px 148px;
            row-gap: 8px;
            column-gap: 9px;
            box-sizing: border-box;
        }
        .tools-and-skills-last-line-wrapper-grid div:last-child {
            grid-column: v-bind('grid.column');
        }
        .tools-and-skills-last-line-wrapper-grid div:nth-last-child(3) > div {
            border-radius: v-bind('thirdElementFromTheEnd')
        }
        .tools-and-skills-last-line-wrapper-grid div:nth-last-child(2) > div {
            border-radius: v-bind('secondElementFromTheEnd')
        }
        .tools-and-skills-last-line-wrapper-grid div:last-child > div {
            border-radius: v-bind('lastElement')
        }
    }
    @media screen and (max-width: 570px) {
        .tools-and-skills-last-line-wrapper-grid {
            display: grid;
            grid-template-columns: 163px 163px;
            column-gap: 8px;
            row-gap: 8px;
            box-sizing: border-box;
        }
        .tools-and-skills-last-line-wrapper-grid div:last-child {
            grid-column: v-bind('grid.column');
        }
        .tools-and-skills-last-line-wrapper-grid div:nth-last-child(2) > div {
            border-radius: v-bind('secondElementFromTheEnd')
        }
        .tools-and-skills-last-line-wrapper-grid div:last-child > div {
            border-radius: v-bind('lastElement')
        }
    }
</style>