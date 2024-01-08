<template>
    <div class="tools-and-skills-first-line-complex-card-wrapper">
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
            width: undefined,
            grid: {
                column: 'span 1'
            },
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
    methods: {
        changeAngle() {
            for (let i = 0; i < this.toolsAndSkillsFirstLineCardArray.length; i += 1) {
                this.toolsAndSkillsFirstLineCardArray[i].radius = "0px 0px 0px 0px"
            }
            if (this.width >= 1190) {
                let test = Math.abs(this.toolsAndSkillsFirstLineCardArray.length % 3 - 3)
                if (test === 1) {
                    this.grid.column = 'span 2'
                    this.toolsAndSkillsFirstLineCardArray[0].radius = "10px 0px 0px 0px"
                    this.toolsAndSkillsFirstLineCardArray[1].radius = "0px 10px 0px 0px"
                }
                if (test === 2) {
                    this.grid.column = 'span 3'
                    this.toolsAndSkillsFirstLineCardArray[0].radius = "10px 10px 0px 0px"
                }
                if (test === 3) {
                    this.grid.column = 'span 1'
                    this.toolsAndSkillsFirstLineCardArray[0].radius = "10px 0px 0px 0px"
                    this.toolsAndSkillsFirstLineCardArray[2].radius = "0px 10px 0px 0px"
                }
            }
            if (this.width >= 950 && this.width < 1190) {
                let test = Math.abs(this.toolsAndSkillsFirstLineCardArray.length % 2 - 2)
                if (test === 2) {
                    this.grid.column = 'span 1'
                    this.toolsAndSkillsFirstLineCardArray[0].radius='10px 0px 0px 0px'
                    this.toolsAndSkillsFirstLineCardArray[1].radius='0px 10px 0px 0px'
                }
                if (test === 1) {
                    this.grid.column = 'span 2'
                    this.toolsAndSkillsFirstLineCardArray[0].radius='10px 0px 0px 0px'
                    this.toolsAndSkillsFirstLineCardArray[1].radius='0px 10px 0px 0px'
                }
            }
            if (this.width < 950) {
                if (this.toolsAndSkillsFirstLineCardArray.length === 1) {
                    this.toolsAndSkillsFirstLineCardArray[0].radius = "10px 10px 10px 10px"
                } else {
                    this.toolsAndSkillsFirstLineCardArray[0].radius = "10px 10px 0px 0px"
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
    }    
    @media screen and (min-width: 950px) and (max-width: 1189px)  {
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
    }
    @media screen and (min-width: 300px) and (max-width: 949px)  {
        .tools-and-skills-first-line-complex-card-wrapper {
            display: grid;
            grid-template-columns: 227px;            
            column-gap: 8px;
            row-gap: 8px;
            box-sizing: border-box;
            width: 227px
        }
    }
</style>