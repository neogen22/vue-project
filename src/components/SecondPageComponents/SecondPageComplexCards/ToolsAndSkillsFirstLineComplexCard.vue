<template>
    <div class="wrapper">
    <ToolsAndSkillsFirstLineCard 
        technology="Figma" 
        technologyFor="UI Design, prototyping"
        radius="5px 0px 0px 0px"
        image="FigmaLogo.svg"
        />
    <ToolsAndSkillsFirstLineCard 
        technology="Java" 
        technologyFor="Software Development"
        image="JavaLogo.svg"
        widthOfSVG="70.5px"
        heightOfSVG="54.5px"
        />
    <ToolsAndSkillsFirstLineCard 
        technology="Python" 
        technologyFor="Design workspace"        
        radius="0px 5px 0px 0px"
        image="PythonLogo.svg"
        widthOfSVG="60.5px"
        heightOfSVG="60px"
        />
    </div>    
</template>

<script>
import ToolsAndSkillsFirstLineCard from '../SecondPageCards/ToolsAndSkillsFirstLineCard.vue'
export default {
    components: {
        ToolsAndSkillsFirstLineCard,
    },
}
</script>

<style scoped>
    .wrapper {
        display: flex; 
        flex-direction: row !important; 
        column-gap: 8px; 
    }
</style>