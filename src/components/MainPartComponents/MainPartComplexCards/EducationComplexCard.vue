<template>
    <div class="education-complex-card-wrapper" ref="educationRef">
        <div v-for="item in educationCardArray" :key="item.id">
            <EducationCard
                :university="item.university"
                :years="item.years" 
                :percentage="item.percentage"
                :image="item.image"
                :scienceDegree="item.scienceDegree"
            />
        </div>
    </div>
</template>

<script>
import EducationCard from '../MainPartCards/EducationCard.vue';
export default {   
    components: {
        EducationCard 
    },    
    data() {
        return {
            width: undefined,
            reacted: 0,
            radiusOfTheFirstElement: '0px 0px 0px 0px',
            radiusOfTheFirstElementOfTheLastLine: '0px 0px 0px 0px',
            radiusOfTheLastElementOfTheLastLine: '0px 0px 0px 0px',
            radiusOfTheSecondElementOfTheLastline: '0px 0px 0px 0px',
            radiusOfTheThirdElement: '0px 0px 0px 0px',
            radiusOfTheSecondElement: '0px 0px 0px 0px',
            grid: {
                column: 'span 1'
            },
            educationCardArray: [
                {
                    university:"Chandigarh University",
                    years:"2020 - 2024",
                    percentage:" - 9 CGPA", 
                    image:"ChandigarhUniversity.svg", 
                    scienceDegree:"Bachelor in Computer Science Engineering",
                },
                {
                    university:"Suditi Global Academy",
                    years:"2018 - 2020",
                    percentage:" - 85%",
                    image:"preview.svg",
                    scienceDegree:"Intermediate XI - XII (CBSE)",
                },
                {
                    university:"Akanksha Global Acadmey", 
                    years:"2016 - 2018", 
                    percentage:" - 92%", 
                    image:"SuditiGlobalAcadem.svg", 
                    scienceDegree:"High School IX - X (CBSE)", 
                },
            ]
        }
    },
    methods: {
        resetRadius() {
            this.radiusOfTheFirstElement= '0px 0px 0px 0px'
            this.radiusOfTheSecondElement='0px 0px 0px 0px'
            this.radiusOfTheThirdElement='0px 0px 0px 0px'
            this.radiusOfTheFirstElementOfTheLastLine= '0px 0px 0px 0px'
            this.radiusOfTheLastElementOfTheLastLine= '0px 0px 0px 0px'
            this.radiusOfTheSecondElementOfTheLastline = '0px 0px 0px 0px'
        },
        changeAngleA() {
            let lengthOfEducationCardArray = document.querySelectorAll('.education-card').length
            if (this.width > 1190) {
                let test = Math.abs(lengthOfEducationCardArray % 3 - 3)
                if (test === 1) {
                    this.resetRadius()
                    if (lengthOfEducationCardArray  === 2) {
                        this.grid.column = 'span 1'
                        this.radiusOfTheFirstElement = '20px 0px 0px 20px'
                        this.radiusOfTheLastElementOfTheLastLine = "0px 20px 20px 0px"
                    }
                    if (lengthOfEducationCardArray  > 3) {
                        this.grid.column = 'span 2'
                        if (lengthOfEducationCardArray % 2 !== 0) {
                            this.radiusOfTheFirstElement = '20px 0px 0px 0px'
                            this.radiusOfTheSecondElementOfTheLastline = '0px 0px 0px 20px'
                            this.radiusOfTheLastElementOfTheLastLine = "0px 0px 20px 0px"
                            this.radiusOfTheThirdElement='0px 20px 0px 0px'
                            this.radiusOfTheThirdElement = "0px 20px 0px 0px"
                        } else {
                            this.radiusOfTheFirstElement = '20px 0px 0px 0px'
                            this.radiusOfTheThirdElement = "0px 20px 0px 0px"
                            this.radiusOfTheLastElementOfTheLastLine = "0px 0px 20px 0px"
                            this.radiusOfTheSecondElementOfTheLastline = '0px 0px 0px 20px'
                        }
                    }
                }
                if (test === 2) {
                    this.resetRadius()
                    this.grid.column = 'span 3'
                    if (lengthOfEducationCardArray === 1) {
                        this.radiusOfTheLastElementofTheLastLine = "20px 20px 20px 20px"
                    } else {
                        this.radiusOfTheFirstElement = "20px 0px 0px 0px"
                        this.radiusOfTheLastElementOfTheLastLine = "0px 0px 20px 20px"
                        this.radiusOfTheThirdElement = "0px 20px 0px 0px"
                    }
                }
                if (test === 3) {
                    this.resetRadius()
                    if (lengthOfEducationCardArray  === 3) {
                        this.grid.column = 'span 1'
                        this.radiusOfTheFirstElementOfTheLastLine = "20px 0px 0px 20px"
                        this.radiusOfTheThirdElement = '0px 20px 20px 0px'
                    }
                    if (lengthOfEducationCardArray  > 3) {
                        this.grid.column = 'span 1'
                        this.radiusOfTheFirstElement = "20px 0px 0px 0px"
                        this.radiusOfTheThirdElement = "0px 20px 0px 0px"
                        this.radiusOfTheFirstElementOfTheLastLine = "0px 0px 0px 20px"
                        this.radiusOfTheLastElementOfTheLastLine = '0px 0px 20px 0px'
                    }
                }
            }
            if ((this.width >= 950 && this.width <= 1190) || (this.width >= 570 && this.width <= 800)) {
                this.resetRadius()
                if (lengthOfEducationCardArray === 1) {
                    this.grid.column = 'span 2'
                    this.radiusOfTheFirstElement= '20px 20px 20px 20px'
                }
                if (lengthOfEducationCardArray === 2) {
                    this.grid.column = 'span 1'
                    this.radiusOfTheFirstElement= '0px 20px 20px 0px'
                    this.radiusOfTheSecondElementOfTheLastline = '20px 0px 0px 20px'
                }
                if (lengthOfEducationCardArray > 2 && lengthOfEducationCardArray % 2 !== 0) {
                    this.grid.column = 'span 2'
                    this.radiusOfTheFirstElement= '20px 0px 0px 0px'
                    this.radiusOfTheSecondElement= '0px 20px 0px 0px'
                    this.radiusOfTheLastElementOfTheLastLine='0px 0px 20px 20px'
                }
                if (lengthOfEducationCardArray > 2 && lengthOfEducationCardArray % 2 === 0) {
                    this.grid.column = 'span 1'
                    this.radiusOfTheFirstElement= '20px 0px 0px 0px'
                    this.radiusOfTheSecondElement= '0px 20px 0px 0px'
                    this.radiusOfTheSecondElementOfTheLastline = '0px 0px 0px 20px'
                    this.radiusOfTheLastElementOfTheLastLine='0px 0px 20px 0px'
                }
            }
            if (this.width < 570 || (this.width > 800 && this.width < 950 )) {
                this.resetRadius()
                if (lengthOfEducationCardArray === 1) {
                    this.radiusOfTheFirstElement= '20px 20px 20px 20px'
                }
                if (lengthOfEducationCardArray > 1) {
                    this.grid.column = 'span 1'
                    this.radiusOfTheFirstElement= '20px 20px 0px 0px'
                    this.radiusOfTheLastElementOfTheLastLine='0px 0px 20px 20px'
                }
            }
        }
    },
    watch: {
        width() {
            this.changeAngleA()
        },
        reacted() {
            this.changeAngleA()
        }
    },
    beforeMount() {
        for (let i = 0; i < this.educationCardArray.length; i += 1) {
            this.educationCardArray[i].id = `${i}${this.educationCardArray[i].university}`
        }
    },
    created() {
        this.width = window.innerWidth
        window.addEventListener('resize', () => {
            this.width = window.innerWidth
        })
    },
    mounted() {
        this.changeAngleA()
        const ob = new MutationObserver(() => {            
            this.reacted += 1
        })        
        ob.observe(this.$refs.educationRef, {childList: true})
    }
}
</script>

<style scoped>   
    @media screen and (min-width: 1190px) {
        .education-complex-card-wrapper {
            display: grid;
            grid-template-columns: repeat(auto-fit, 227px);
            column-gap: 8px;
            row-gap: 8px;            
            padding-bottom: 48px;            
            box-sizing: border-box;
            max-width: 800px;            
        }
        .education-complex-card-wrapper div:last-child {
            grid-column: v-bind('grid.column');
        }
        .education-complex-card-wrapper div > div {
            border-radius: '0px 0px 0px 0px';
        }
        .education-complex-card-wrapper div:nth-last-child(2) > div {
            border-radius: v-bind('radiusOfTheSecondElementOfTheLastline');
        }
        .education-complex-card-wrapper div:first-child > div {
            border-radius: v-bind('radiusOfTheFirstElement');
        }
        .education-complex-card-wrapper div:nth-last-child(3) > div {
            border-radius: v-bind('radiusOfTheFirstElementOfTheLastLine');
        }
        .education-complex-card-wrapper div:last-child > div {
            border-radius: v-bind('radiusOfTheLastElementOfTheLastLine');
        }
        .education-complex-card-wrapper div:nth-child(3) > div {
            border-radius: v-bind('radiusOfTheThirdElement');
        }
    }
    @media screen and (min-width: 800px) and (max-width: 1190px)  {
        .education-complex-card-wrapper {
            display: grid;
            grid-template-columns: repeat(auto-fit, 227px);
            max-width: 600px;
            column-gap: 8px;
            row-gap: 8px;            
            padding-bottom: 48px;            
            box-sizing: border-box;
        }
        .education-complex-card-wrapper div:last-child {
            grid-column: v-bind('grid.column');
        }
        .education-complex-card-wrapper div:first-child > div {
            border-radius: v-bind('radiusOfTheFirstElement');
        }
        .education-complex-card-wrapper div:nth-child(2) > div {
            border-radius: v-bind('radiusOfTheSecondElement');
        }
        .education-complex-card-wrapper div:nth-last-child(2) > div {
            border-radius: v-bind('radiusOfTheSecondElementOfTheLastline');
        }
        .education-complex-card-wrapper div:last-child > div {
            border-radius: v-bind('radiusOfTheLastElementOfTheLastLine');
        }
        .education-complex-card-wrapper div:nth-child(2) > div {
            border-radius: v-bind('radiusOfTheSecondElement');
        }
    }
    @media screen and (min-width: 800px) and (max-width: 950px)  {
        .education-complex-card-wrapper {
            display: flex;
            flex-direction: column;
            column-gap: 8px;
            row-gap: 8px;            
            padding-bottom: 3vh;            
            box-sizing: border-box;
            padding-bottom: 5vh;
        }
        .education-complex-card-wrapper div > div {
            width: 332px;
        }
        .education-complex-card-wrapper div:first-child > div {
            border-radius: v-bind('radiusOfTheFirstElement');
        }
        .education-complex-card-wrapper div:last-child > div {
            border-radius: v-bind('radiusOfTheLastElementOfTheLastLine');
        }
    }
    @media screen and (min-width: 570px) and (max-width: 800px)  {
        .education-complex-card-wrapper {
            display: grid;
            grid-template-columns: repeat(auto-fit, 227px);
            max-width: 600px;
            column-gap: 8px;
            row-gap: 8px;            
            padding-bottom: 48px;            
            box-sizing: border-box;
        }
        .education-complex-card-wrapper div:last-child {
            grid-column: v-bind('grid.column');
        }
        .education-complex-card-wrapper div:first-child > div {
            border-radius: v-bind('radiusOfTheFirstElement');
        }
        .education-complex-card-wrapper div:nth-child(2) > div {
            border-radius: v-bind('radiusOfTheSecondElement');
        }
        .education-complex-card-wrapper div:nth-last-child(2) > div {
            border-radius: v-bind('radiusOfTheSecondElementOfTheLastline');
        }
        .education-complex-card-wrapper div:last-child > div {
            border-radius: v-bind('radiusOfTheLastElementOfTheLastLine');
        }
        .education-complex-card-wrapper div:nth-child(2) > div {
            border-radius: v-bind('radiusOfTheSecondElement');
        }
    }
    @media screen and (max-width: 570px) {
        .education-complex-card-wrapper {
            display: flex;
            flex-direction: column;
            column-gap: 8px;
            row-gap: 8px;            
            padding-bottom: 3vh;            
            box-sizing: border-box;
            padding-bottom: 5vh;
        }
        .education-complex-card-wrapper div > div {
            width: 332px;
        }
        .education-complex-card-wrapper div:first-child > div {
            border-radius: v-bind('radiusOfTheFirstElement');
        }
        .education-complex-card-wrapper div:last-child > div {
            border-radius: v-bind('radiusOfTheLastElementOfTheLastLine');
        }
    }
</style>