<template>
        <div class="tools-and-skills-last-line-wrapper-grid">
            <div v-for="item in toolsAndSkillsLastLineCardArray" :key="item.id">
                <ToolsAndSkillsLastLineCard
                    :technology="item.technology"
                    :technologyFor="item.technologyFor"
                    :image="item.image"
                    :radius="item.radius"
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
                portrait: false,
                width: 0,
                height: 0,
                grid: {
                    column: 'span 1'
                },
                toolsAndSkillsLastLineCardArray: [
                    {
                        technology:"HTML 5",
                        technologyFor:"Structural Design",
                        image:"HTML5Logo.svg",
                        radius:"0px 0px 0px 5px",
                        widthOfSVG:"60px",
                        heightOfSVG:"55px"
                    },
                    {
                        technology:"CSS 3",
                        technologyFor:"Style Design",
                        image:"CSS3Logo.svg",
                        radius:"0px 0px 0px 0px",
                        widthOfSVG:"63px",
                        heightOfSVG:"66px",
                    },
                    {
                        technology:"Wordpress",
                        technologyFor:"Web development",
                        image:"WordPressLogo.svg",
                        radius:"0px 0px 0px 0px",
                        widthOfSVG:"68px",
                        heightOfSVG:"61px",
                    },
                    {
                        technology:"VS Code",
                        technologyFor:"Code editor",
                        image:"VSCodeJPG.png",
                        radius:"0px 0px 0px 0px",
                        widthOfSVG:"32px",
                        heightOfSVG:"32px",
                    },
                    {
                        technology:"Notion",
                        technologyFor:"Project managment",
                        image:"NotionLogo.svg",
                        radius:"0px 0px 5px 0px",
                        widthOfSVG:"32px",
                        heightOfSVG:"32px",
                    },
                ]
            }
        },        
        mounted() {
            this.height = window.innerHeight
            this.width=window.innerWidth
            if (this.height > this.width) {
                this.portrait = true
            }
            if (this.toolsAndSkillsLastLineCardArray.length % 2 !== 0) {
                this.grid.column = 'span 2'
            }
        },
    }
</script>

<style scoped>
    @media (orientation: portrait) {
        .tools-and-skills-last-line-wrapper-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 6px;
        }
        .tools-and-skills-last-line-wrapper-grid div:last-child {
            grid-column: v-bind('grid.column');
        }  
    }
    @media (orientation: landscape) {
        .tools-and-skills-last-line-wrapper-grid {
            display: grid;
            grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
            gap: 6px;
        }
    }
</style>