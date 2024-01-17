<template>
    <div class="tools-and-skills-first-line-complex-card-wrapper" ref="toolsFirstLineRef">
        <div v-for="item in toolsAndSkillsFirstLineCardArray" :key="item.id">
            <ToolsAndSkillsFirstLineCard 
                :technology="item.technology" 
                :technologyFor="item.technologyFor"
                :radius="item.radius"
                :image="item.image"
                :widthOfSVG="item.widthOfSVG"
                :heightOfSVG="item.heightOfSVG"
            />
        </div>
    </div>
</template>

<script>
import ToolsAndSkillsFirstLineCard from '../MainPartCards/ToolsAndSkillsFirstLineCard.vue'
export default {
    components: {
        ToolsAndSkillsFirstLineCard,
    },
    data() {
        return {
            reacted: 0,
            width: undefined,
            grid: {
                column: 'span 1'
            },
            radiusOfTheFirstElement: '0px 0px 0px 0px',
            radiusOfTheSecondElement: '0px 0px 0px 0px',
            radiusOfTheThirdElement: '0px 0px 0px 0px',
            toolsAndSkillsFirstLineCardArray: [
                {
                    technology:"Figma", 
                    technologyFor:"UI Design, prototyping",
                    image:"FigmaLogo.svg"
                },
                {
                    technology:"Java", 
                    technologyFor:"Software Development",
                    image:"JavaLogo.svg",
                    widthOfSVG:"71px",
                    heightOfSVG:"55px"
                },
                {
                    technology:"Python", 
                    technologyFor:"Design workspace",
                    image:"PythonLogo.svg",
                    widthOfSVG:"61px",
                    heightOfSVG:"60px"
                },
            ],
        }
    },
    methods: {
        resetAngles() {
            this.radiusOfTheFirstElement = '0px 0px 0px 0px'
            this.radiusOfTheSecondElement = '0px 0px 0px 0px'
            this.radiusOfTheThirdElement = '0px 0px 0px 0px'
        },
        changeAngle() {
            const lengthOfToolsFirstLine = document.querySelectorAll('.tool-flex-card-first-line-card').length
            if (this.width > 1190) {
                this.resetAngles()
                let test = Math.abs(lengthOfToolsFirstLine % 3 - 3)
                if (test === 1) {
                    if (lengthOfToolsFirstLine === 2) {
                        this.grid.column = 'span 2'
                        this.radiusOfTheFirstElement = '20px 0px 0px 0px'
                        this.radiusOfTheSecondElement = '0px 20px 0px 0px'
                    }
                    if (lengthOfToolsFirstLine > 3) {
                        this.grid.column = 'span 2'
                        if (lengthOfToolsFirstLine % 2 !== 0) {
                            this.radiusOfTheFirstElement = '20px 0px 0px 0px'
                            this.radiusOfTheThirdElement='0px 20px 0px 0px'
                            this.radiusOfTheThirdElement = "0px 20px 0px 0px"
                        } else {
                            this.radiusOfTheFirstElement = '20px 0px 0px 0px'
                            this.radiusOfTheThirdElement = "0px 20px 0px 0px"
                        }
                    }
                }
                if (test === 2) {
                    this.grid.column = 'span 3'
                    if (lengthOfToolsFirstLine === 1) {
                        this.radiusOfTheFirstElement = "20px 20px 20px 20px"
                    } else {
                        this.radiusOfTheFirstElement = "20px 0px 0px 0px"
                        this.radiusOfTheThirdElement = "0px 20px 0px 0px"
                    }
                }
                if (test === 3) {
                    if (lengthOfToolsFirstLine === 3) {
                        this.grid.column = 'span 1'
                        this.radiusOfTheFirstElement = "20px 0px 0px 0px"
                        this.radiusOfTheThirdElement = '0px 20px 0px 0px'
                    }
                    if (lengthOfToolsFirstLine > 3) {
                        this.grid.column = 'span 1'
                        this.radiusOfTheFirstElement = "20px 0px 0px 0px"
                        this.radiusOfTheThirdElement = "0px 20px 0px 0px"
                    }
                }
            }
            if ((this.width >= 950 && this.width <= 1190) || (this.width >= 570 && this.width <= 800)) {
                this.resetAngles()
                if (lengthOfToolsFirstLine === 1) {
                    this.grid.column = 'span 2'
                    this.radiusOfTheFirstElement= '20px 20px 20px 20px'
                }
                if (lengthOfToolsFirstLine === 2) {
                    this.grid.column = 'span 1'
                    this.radiusOfTheFirstElement= '0px 20px 20px 0px'
                }
                if (lengthOfToolsFirstLine > 2 && lengthOfToolsFirstLine % 2 !== 0) {
                    this.grid.column = 'span 2'
                    this.radiusOfTheFirstElement= '20px 0px 0px 0px'
                    this.radiusOfTheSecondElement= '0px 20px 0px 0px'
                }
                if (lengthOfToolsFirstLine > 2 && lengthOfToolsFirstLine % 2 === 0) {
                    this.grid.column = 'span 1'
                    this.radiusOfTheFirstElement= '20px 0px 0px 0px'
                    this.radiusOfTheSecondElement= '0px 20px 0px 0px'
                }
            }
            if (this.width < 570 || (this.width > 800 && this.width < 950)) {
                this.resetAngles()
                if (lengthOfToolsFirstLine === 1) {
                    this.grid.column = 'span 2'
                    this.radiusOfTheFirstElement= '20px 20px 20px 20px'
                }
                if (lengthOfToolsFirstLine === 2) {
                    this.grid.column = 'span 1'
                    this.radiusOfTheFirstElement= '0px 20px 20px 0px'
                }
                if (lengthOfToolsFirstLine > 2 && lengthOfToolsFirstLine % 2 !== 0) {
                    this.grid.column = 'span 2'
                    this.radiusOfTheFirstElement= '20px 0px 0px 0px'
                    this.radiusOfTheSecondElement= '0px 20px 0px 0px'
                }
                if (lengthOfToolsFirstLine > 2 && lengthOfToolsFirstLine % 2 === 0) {
                    this.grid.column = 'span 1'
                    this.radiusOfTheFirstElement= '20px 0px 0px 0px'
                    this.radiusOfTheSecondElement= '0px 20px 0px 0px'
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
        for (let i = 0; i < this.toolsAndSkillsFirstLineCardArray.length; i += 1) {
            this.toolsAndSkillsFirstLineCardArray[i].id = `${i}${this.toolsAndSkillsFirstLineCardArray[i].technology}`
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
        const toolsFirstLineObserver = new MutationObserver(() => {
            this.reacted += 1
        })
        toolsFirstLineObserver.observe(this.$refs.toolsFirstLineRef, {childList: true})
    },
}
</script>

<style scoped>
    @media screen and (min-width: 1190px) {
        .tools-and-skills-first-line-complex-card-wrapper {
            display: grid;
            grid-template-columns: 227px 227px 227px;
            column-gap: 8px;
            row-gap: 8px;
            box-sizing: border-box;
            width: 700px
        }
        .tools-and-skills-first-line-complex-card-wrapper div:last-child {
            grid-column: v-bind('grid.column');
        }
        .tools-and-skills-first-line-complex-card-wrapper div:last-child {
            grid-column: v-bind('grid.column');
        }
        .tools-and-skills-first-line-complex-card-wrapper div > div {
            border-radius: '0px 0px 0px 0px';
        }
        .tools-and-skills-first-line-complex-card-wrapper div:first-child > div {
            border-radius: v-bind('radiusOfTheFirstElement');
        }
        .tools-and-skills-first-line-complex-card-wrapper div:nth-child(2) > div {
            border-radius: v-bind('radiusOfTheSecondElement');
        }
        .tools-and-skills-first-line-complex-card-wrapper div:nth-child(3) > div {
            border-radius: v-bind('radiusOfTheThirdElement');
        }
    }
    @media screen and (min-width: 950px) and (max-width: 1190px) {
        .tools-and-skills-first-line-complex-card-wrapper {
            display: grid;
            grid-template-columns: 227px 227px;
            column-gap: 8px;
            row-gap: 8px;
            box-sizing: border-box;
        }
        .tools-and-skills-first-line-complex-card-wrapper div:last-child {
            grid-column: v-bind('grid.column');
        }
        .tools-and-skills-first-line-complex-card-wrapper div:first-child > div {
            border-radius: v-bind('radiusOfTheFirstElement');
        }
        .tools-and-skills-first-line-complex-card-wrapper div:nth-child(2) > div {
            border-radius: v-bind('radiusOfTheSecondElement');
        }
    }
    @media screen and (min-width: 800px) and (max-width: 950px) {
        .tools-and-skills-first-line-complex-card-wrapper {
            display: grid;
            grid-template-columns: 163px 163px;
            column-gap: 8px;
            row-gap: 8px;
            box-sizing: border-box;
        }
        .tools-and-skills-first-line-complex-card-wrapper div:last-child {
            grid-column: v-bind('grid.column');
        }
        .tools-and-skills-first-line-complex-card-wrapper div:first-child > div {
            border-radius: v-bind('radiusOfTheFirstElement');
        }
        .tools-and-skills-first-line-complex-card-wrapper div:nth-child(2) > div {
            border-radius: v-bind('radiusOfTheSecondElement');
        }
    }
    @media screen and (min-width: 570px) and (max-width: 800px) {
        .tools-and-skills-first-line-complex-card-wrapper {
            display: grid;
            grid-template-columns: 227px 227px;
            column-gap: 8px;
            row-gap: 8px;
            box-sizing: border-box;
        }
        .tools-and-skills-first-line-complex-card-wrapper div:last-child {
            grid-column: v-bind('grid.column');
        }
        .tools-and-skills-first-line-complex-card-wrapper div:first-child > div {
            border-radius: v-bind('radiusOfTheFirstElement');
        }
        .tools-and-skills-first-line-complex-card-wrapper div:nth-child(2) > div {
            border-radius: v-bind('radiusOfTheSecondElement');
        }
    }
    @media screen and (min-width: 300px) and (max-width: 570px) {
        .tools-and-skills-first-line-complex-card-wrapper {
            display: grid;
            grid-template-columns: 163px 163px;
            column-gap: 8px;
            row-gap: 8px;
            box-sizing: border-box;
        }
        .tools-and-skills-first-line-complex-card-wrapper div:last-child {
            grid-column: v-bind('grid.column');
        }
        .tools-and-skills-first-line-complex-card-wrapper div:first-child > div {
            border-radius: v-bind('radiusOfTheFirstElement');
        }
        .tools-and-skills-first-line-complex-card-wrapper div:nth-child(2) > div {
            border-radius: v-bind('radiusOfTheSecondElement');
        }
    }
</style>