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
    @media screen and (min-width: 1190px) {
        .tools-and-skills-complex-card-wrapper {
            display: flex;
            flex-direction: column;
            row-gap: 8px;
            width: 85vw;
            padding-bottom: 48px;
            width: 700px
        }
    }
    @media screen and (min-width: 950px) and (max-width: 1190px) {
        .tools-and-skills-complex-card-wrapper {
            display: flex;
            flex-direction: column;
            row-gap: 8px;
            width: 462px;
            padding-bottom: 48px;
        }
    }
    @media screen and (min-width: 300px) and (max-width: 950px) {
        .tools-and-skills-complex-card-wrapper {
            display: flex;
            flex-direction: column;
            row-gap: 8px;
            padding-bottom: 5vh;
        }
    }
</style>