<template>
    <div class="wrapper">
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
.wrapper {
    display: flex; 
    flex-direction: column; 
    row-gap: 8px; 
    width: 698px;
}
</style>