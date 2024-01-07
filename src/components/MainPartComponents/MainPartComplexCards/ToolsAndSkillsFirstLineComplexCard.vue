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
            portrait: false,
            width: 0,
            height: 0,
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
    mounted() {
        for (let i = 0; i < this.toolsAndSkillsFirstLineCardArray.length; i += 1) {
            this.toolsAndSkillsFirstLineCardArray[i].id = `${i}${this.toolsAndSkillsFirstLineCardArray[i].technology}`
        }
        if (window.innerHeight > window.innerWidth) {
            this.portrait = true
        } else {
            this.portrait = false
        }
        if (this.portrait) {
            this.toolsAndSkillsFirstLineCardArray[0].radius = "15px 15px 0px 0px"
        } else {
            this.toolsAndSkillsFirstLineCardArray[0].radius = "5px 0px 0px 0px"
            this.toolsAndSkillsFirstLineCardArray[this.toolsAndSkillsFirstLineCardArray.length - 1].radius = "0px 5px 0px 0px"
        }
    }
}
</script>

<style scoped>
    @media (orientation: portrait) {
        .tools-and-skills-first-line-complex-card-wrapper {
            display: flex; 
            flex-direction: column; 
            row-gap: 8px;
            flex-wrap: wrap;
        }
    }
    @media (orientation: landscape) {
        .tools-and-skills-first-line-complex-card-wrapper {
            display: flex; 
            flex-direction: row; 
            column-gap: 8px;
            flex-wrap: wrap;
        }
    }
</style>