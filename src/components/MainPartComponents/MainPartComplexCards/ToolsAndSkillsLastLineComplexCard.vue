<template>
    <div class="tools-and-skills-last-line-wrapper">
        <ToolsAndSkillsLastLineCard
            technology="HTML 5"
            technologyFor="Structural Design"
            image="HTML5Logo.svg"
            radius="0px 0px 0px 5px"
            widthOfSVG="60px"
            heightOfSVG="55px"
            />
        <ToolsAndSkillsLastLineCard
            technology="CSS 3"
            technologyFor="Style Design"
            image="CSS3Logo.svg"
            radius="0px 0px 0px 0px"
            widthOfSVG="63px"
            heightOfSVG="66px"            
            />
        <ToolsAndSkillsLastLineCard
            technology="Wordpress"
            technologyFor="Web development"
            image="WordPressLogo.svg"
            radius="0px 0px 0px 0px"
            widthOfSVG="68px"
            heightOfSVG="61px"            
            />
        <ToolsAndSkillsLastLineCard
            technology="VS Code"
            technologyFor="Code editor"
            image="VSCodeJPG.png"
            radius="0px 0px 0px 0px"
            widthOfSVG="32px"
            heightOfSVG="32px" 
            />
        <ToolsAndSkillsLastLineCard 
            technology="Notion"
            technologyFor="Project managment"
            image="NotionLogo.svg"
            radius="0px 0px 5px 0px"
            widthOfSVG="32px"
            heightOfSVG="32px" 
            />
    </div>    
</template>

<script>
    import ToolsAndSkillsLastLineCard from '../MainPartCards/ToolsAndSkillsLastLineCard.vue';
    export default {
        components: {
            ToolsAndSkillsLastLineCard,
        },
    }
</script>

<style scoped>
    @media (orientation: portrait) {
        .tools-and-skills-last-line-wrapper {
            display: flex; 
            flex-direction: row !important; 
            row-gap: 8px;
            flex-wrap: wrap;
            column-gap: 8px;
            width: 85vw;
            justify-content: space-around;
        }
    }
    @media (orientation: landscape) {
        .tools-and-skills-last-line-wrapper {
            display: flex; 
            flex-direction: row !important; 
            column-gap: 8px;
            flex-wrap: wrap;
        }
    }
</style>