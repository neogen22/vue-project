<template>
    <div class="wrapper">
        <CertificatesAndAwardCard
            school="freeCodeCamp"
            course="Responsive Web Design"
            dates="Dec 2021 - Feb 2022"
            image="ResponsiveWebIcon.svg"
            widthOfSVG="43.5px"
            heightOfSVG="43.5px"
            radius="5px 5px 0px 0px"
        />
        <CertificatesAndAwardCard
            school="Google"
            course="Data Strcture & Algorithms"
            dates="Mar 2021 - Jun 2021"
            image="GoogleIconS.svg"
            widthOfSVG="47.4px"
            heightOfSVG="47.4px"
            radius="0px 0px 5px 5px"
        />       
    </div>    
</template>

<script>
    import CertificatesAndAwardCard from '../SecondPageCards/CertificatesAndAwardsCard.vue'
    export default {
        components: {
            CertificatesAndAwardCard
        }
    }
</script>

<style scoped>
    .wrapper {
        display: flex; 
        flex-direction: column; 
        row-gap: 8.07px;        
        box-sizing: border-box;
        padding: 0px 24.2px;
        width: 696px; 
        height: auto;
    }
</style>