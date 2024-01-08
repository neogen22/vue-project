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
                width: undefined,                
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
        methods: {
            changeAngle() {
                for (let i = 0; i < this.toolsAndSkillsLastLineCardArray.length; i += 1) {
                    this.toolsAndSkillsLastLineCardArray[i].radius = "0px 0px 0px 0px"
                }
                if (this.width >= 1190) {
                    let test = Math.abs(this.toolsAndSkillsLastLineCardArray.length % 5 - 5)
                    if (test === 4) {
                        this.grid.column = 'span 5'
                        this.toolsAndSkillsLastLineCardArray[this.toolsAndSkillsLastLineCardArray.length - 1].radius = "0px 0px 10px 10px"
                    }
                    if (test === 3) {
                        this.grid.column = 'span 4'
                        this.toolsAndSkillsLastLineCardArray[this.toolsAndSkillsLastLineCardArray.length - 1].radius = "0px 0px 10px 0px"
                        this.toolsAndSkillsLastLineCardArray[this.toolsAndSkillsLastLineCardArray.length - 2].radius = "0px 0px 0px 10px"
                    }
                    if (test === 2) {
                        this.grid.column = 'span 3'
                        this.toolsAndSkillsLastLineCardArray[this.toolsAndSkillsLastLineCardArray.length - 1].radius = "0px 0px 10px 0px"
                        this.toolsAndSkillsLastLineCardArray[this.toolsAndSkillsLastLineCardArray.length - 3].radius = "0px 0px 0px 10px"
                    }
                    if (test === 1) {
                        this.grid.column = 'span 2'
                        this.toolsAndSkillsLastLineCardArray[this.toolsAndSkillsLastLineCardArray.length - 1].radius = "0px 0px 10px 0px"
                        this.toolsAndSkillsLastLineCardArray[this.toolsAndSkillsLastLineCardArray.length - 4].radius = "0px 0px 0px 10px"
                    }
                    if (test === 5) {
                        this.grid.column = 'span 1'
                        this.toolsAndSkillsLastLineCardArray[this.toolsAndSkillsLastLineCardArray.length - 1].radius = "0px 0px 10px 0px"
                        this.toolsAndSkillsLastLineCardArray[this.toolsAndSkillsLastLineCardArray.length - 5].radius = "0px 0px 0px 10px"
                    }
                }
                if (this.width >= 950 && this.width < 1190) {
                    let test = Math.abs(this.toolsAndSkillsLastLineCardArray.length % 3 - 3)
                    if (test === 1) {
                        this.grid.column = 'span 2'
                        this.toolsAndSkillsLastLineCardArray[this.toolsAndSkillsLastLineCardArray.length - 1].radius = "0px 0px 10px 0px"
                        this.toolsAndSkillsLastLineCardArray[this.toolsAndSkillsLastLineCardArray.length - 2].radius = "0px 0px 0px 10px"
                    }
                    if (test === 2) {
                        this.grid.column = 'span 3'
                        this.toolsAndSkillsLastLineCardArray[this.toolsAndSkillsLastLineCardArray.length - 1].radius = "0px 0px 10px 10px"
                    }
                    if (test === 3) {
                        this.grid.column = 'span 1'
                        this.toolsAndSkillsLastLineCardArray[this.toolsAndSkillsLastLineCardArray.length - 1].radius = "0px 0px 10px 0px"
                        this.toolsAndSkillsLastLineCardArray[this.toolsAndSkillsLastLineCardArray.length - 3].radius = "0px 0px 0px 10px"
                    }
                }
                if (this.width < 950) {
                    this.toolsAndSkillsLastLineCardArray[this.toolsAndSkillsLastLineCardArray.length - 1].radius = "0px 0px 10px 10px"
                }
            }
        },
        watch: {
            width() {
                this.changeAngle()
            },
        }
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
    }    
    @media screen and (min-width: 950px) and (max-width: 1189px)  {
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
    }
    @media screen and (min-width: 300px) and (max-width: 949px)  {
        .tools-and-skills-last-line-wrapper-grid {
            display: grid;
            grid-template-columns: 227px;            
            column-gap: 8px;
            row-gap: 8px;
            box-sizing: border-box;
        }
    }
</style>