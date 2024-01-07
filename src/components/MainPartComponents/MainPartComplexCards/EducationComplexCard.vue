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
            portrait: undefined,
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
                }
            ]
        }
    },
    beforeMount() {
        for (let i = 0; i < this.educationCardArray.length; i += 1) {
            this.educationCardArray[i].id = `${i}${this.educationCardArray[i].university}`
        }
    },
    mounted() {
        if (window.innerHeight > window.innerWidth) {
            this.portrait = true
        } else {
            this.portrait = false
        }
        if (this.portrait) {
            if (this.educationCardArray.length === 1) {
                this.educationCardArray[0].radius = "15px 15px 15px 15px"
            } else {
                this.educationCardArray[0].radius="15px 15px 0px 0px"
                this.educationCardArray[this.educationCardArray.length - 1].radius="0px 0px 15px 15px"
            }
        } else {
            if (this.educationCardArray.length === 1) {
                this.educationCardArray[0].radius = "5px 5px 5px 5px"
            } else {
                this.educationCardArray[0].radius="5px 0px 0px 5px"
                this.educationCardArray[this.educationCardArray.length - 1].radius="0px 5px 5px 0px"
            }
        }
    }
}
</script>

<style scoped>
    @media (orientation: portrait) {
        .education-complex-card-wrapper {
            display: flex;
            flex-direction: column;
            column-gap: 8px;
            row-gap: 8px;            
            padding-bottom: 3vh;
            width: 80vw;
            flex-wrap: wrap;
            box-sizing: border-box;
        }
    }
    @media(orientation: landscape) {
        .education-complex-card-wrapper {
            display: flex;
            flex-direction: row;
            column-gap: 8px;
            row-gap: 8px;
            padding-bottom: 48px;
            width: 698px;
            flex-wrap: wrap;
        }
    }
</style>