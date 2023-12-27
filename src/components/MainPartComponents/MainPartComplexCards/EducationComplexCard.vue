<template>
    <div class="education-complex-card-wrapper">
        <EducationCard
            university="Chandigarh University" 
            years="2020 - 2024" 
            percentage=" - 9 CGPA" 
            image="ChandigarhUniversity.svg" 
            scienceDegree="Bachelor in Computer Science Engineering" 
            radius="4px 0px 0px 4px"
            wrap="nowrap"
            />
        <EducationCard
            university="Suditi Global Academy" 
            years="2018 - 2020" 
            percentage=" - 85%" 
            image="preview.svg"
            scienceDegree="Intermediate XI - XII (CBSE)"
            radius="0px 0px 0px 0px"
            />
        <EducationCard 
            university="Akanksha Global Acadmey" 
            years="2016 - 2018" 
            percentage=" - 92%" 
            image="SuditiGlobalAcadem.svg" 
            scienceDegree="High School IX - X (CBSE)" 
            radius="0px 4px 4px 0px"
            />
    </div>
</template>

<script>
import EducationCard from '../MainPartCards/EducationCard.vue';
export default {   
    components: {
        EducationCard 
    },
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