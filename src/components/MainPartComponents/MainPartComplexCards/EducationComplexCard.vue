<template>
    <div class="education-complex-card-wrapper">
        <div v-for="item in educationCardArray" :key="item.id">
            <EducationCard
                :university="item.university"
                :years="item.years" 
                :percentage="item.percentage"
                :image="item.image"
                :scienceDegree="item.scienceDegree"
                :radius="item.radius"                                  
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
    methods: {
        changeAngle() {
            for (let i = 0; i < this.educationCardArray.length; i += 1) {
                this.educationCardArray[i].radius = "0px 0px 0px 0px"
            }
            if (this.width >= 1190) {
                let test = Math.abs(this.educationCardArray.length % 3 - 3)
                if (test === 1) {
                    if (this.educationCardArray.length === 2) {
                        this.grid.column = 'span 1'
                        this.educationCardArray[0].radius = "10px 0px 0px 10px"
                        this.educationCardArray[1].radius = "0px 10px 10px 0px"
                    }
                    if (this.educationCardArray.length > 3) {
                        this.grid.column = 'span 2'
                        this.educationCardArray[0].radius = "10px 0px 0px 0px"
                        this.educationCardArray[2].radius = "0px 10px 0px 0px"
                        this.educationCardArray[this.educationCardArray.length - 1].radius = "0px 0px 10px 0px"
                        this.educationCardArray[this.educationCardArray.length - 2].radius = "0px 0px 0px 10px"
                    }
                }
                if (test === 2) {
                    this.grid.column = 'span 3'
                    if (this.educationCardArray.length > 3) {
                        this.educationCardArray[0].radius = "10px 0px 0px 0px"
                        this.educationCardArray[2].radius = "0px 10px 0px 0px"
                        this.educationCardArray[this.educationCardArray.length - 1].radius = "0px 0px 10px 10px"
                    }
                }
                if (test === 3) {
                    if (this.educationCardArray.length === 3) {
                        this.grid.column = 'span 1'
                        this.educationCardArray[0].radius = "10px 0px 0px 10px"
                        this.educationCardArray[2].radius = "0px 10px 10px 0px"
                    }
                    if (this.educationCardArray.length > 3) {
                        this.grid.column = 'span 1'
                        this.educationCardArray[0].radius = "10px 0px 0px 0px"
                        this.educationCardArray[2].radius = "0px 10px 0px 0px"
                        this.educationCardArray[this.educationCardArray.length - 1].radius = "0px 0px 10px 0px"
                        this.educationCardArray[this.educationCardArray.length - 3].radius = "0px 0px 0px 10px"
                    }
                }
            }
            if (this.width >= 950 && this.width < 1190) {
                if (this.educationCardArray.length === 1) {
                    this.educationCardArray[0].radius = "10px 10px 10px 10px"
                }
                if (this.educationCardArray.length === 2) {
                    this.educationCardArray[0].radius = "10px 10px 0px 0px"
                    this.educationCardArray[1].radius = "0px 0px 10px 10px"
                }
                if (this.educationCardArray.length % 2 !== 0 && this.educationCardArray.length !== 1) {
                    this.grid.column = 'span 2'
                    this.educationCardArray[this.educationCardArray.length - 1].radius='0px 0px 10px 10px'
                    this.educationCardArray[0].radius='10px 0px 0px 0px'
                    this.educationCardArray[1].radius='0px 10px 0px 0px'
                }
                if (this.educationCardArray.length % 2 === 0 && this.educationCardArray.length > 2) {
                    this.grid.column = 'span 1'
                    this.educationCardArray[0].radius='10px 0px 0px 0px'
                    this.educationCardArray[1].radius='0px 10px 0px 0px'
                    this.educationCardArray[this.educationCardArray.length - 1].radius='0px 0px 10px 0px'
                    this.educationCardArray[this.educationCardArray.length - 2].radius='0px 0px 0px 10px'
                }
            }
            if (this.width < 950) {
                if (this.educationCardArray.length === 1) {
                    this.educationCardArray[0].radius = "10px 10px 10px 10px"
                } else {
                    this.educationCardArray[0].radius = "10px 10px 0px 0px"
                    this.educationCardArray[this.educationCardArray.length - 1].radius = "0px 0px 10px 10px"
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
        .education-complex-card-wrapper {
            display: grid;
            grid-template-columns: 227px 227px 227px;            
            column-gap: 8px;
            row-gap: 8px;            
            padding-bottom: 48px;            
            box-sizing: border-box;
        }
        .education-complex-card-wrapper div:last-child {
            grid-column: v-bind('grid.column');
        } 
    }
    @media screen and (min-width: 950px) and (max-width: 1190px)  {
        .education-complex-card-wrapper {
            display: grid;
            grid-template-columns: 227px 227px;            
            column-gap: 8px;
            row-gap: 8px;            
            padding-bottom: 48px;            
            box-sizing: border-box;
        }
        .education-complex-card-wrapper div:last-child {
            grid-column: v-bind('grid.column');
        }        
    }
    @media screen and (min-width: 300px) and (max-width: 950px)  {
        .education-complex-card-wrapper {
            display: grid;
            grid-template-columns: 332px;
            column-gap: 8px;
            row-gap: 8px;            
            padding-bottom: 3vh;            
            box-sizing: border-box;
            padding-bottom: 5vh; 
        }
    }
</style>