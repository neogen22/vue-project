<script>
import EducationCard  from '../SecondPageCards/EducationCard.vue';
export default {   
    components: {
        EducationCard 
    },
}
</script>

<template>
    <div class="wrapper">
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

<style scoped>
    .wrapper {
        display: flex;
        flex-direction: row;
        column-gap: 8px;
        padding-bottom: 48.4px;
    }    
</style>