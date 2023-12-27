<template>
    <div class="tools-and-skills-complex-card-wrapper">
        <ToolsAndSkillsFirstLineComplexCard/>
        <ToolsAndSkillsLastLineComplexCard/>
    </div>    
</template>

<script>
    import ToolsAndSkillsFirstLineComplexCard from '../MainPartComplexCards/ToolsAndSkillsFirstLineComplexCard.vue';
    import ToolsAndSkillsLastLineComplexCard from '../MainPartComplexCards/ToolsAndSkillsLastLineComplexCard.vue';
    export default {
        components: {
            ToolsAndSkillsFirstLineComplexCard,
            ToolsAndSkillsLastLineComplexCard
        },
    }
</script>

<style scoped>
@media (orientation: portrait) {
    .tools-and-skills-complex-card-wrapper {
        display: flex; 
        flex-direction: column; 
        row-gap: 8px; 
        width: 85vw;
    }
}
@media (orientation: landscape) {
    .tools-and-skills-complex-card-wrapper {
        display: flex; 
        flex-direction: column; 
        row-gap: 8px; 
        width: 698px;
    }
}
</style>