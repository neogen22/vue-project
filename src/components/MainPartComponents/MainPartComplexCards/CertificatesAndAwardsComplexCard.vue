<template>
    <div class="wrapper">
        <div v-for="item in certificatesAndAwardCardArray" :key="item">
            <CertificatesAndAwardCard
                :school="item.school"
                :course="item.course"
                :dates="item.dates"
                :image="item.image"
                :widthOfSVG="item.widthOfSVG"
                :heightOfSVG="item.heightOfSVG"
                :radius="item.radius"
            />
        </div>
    </div>    
</template>

<script>
    import CertificatesAndAwardCard from '../MainPartCards/CertificatesAndAwardsCard.vue'
    export default {
        components: {
            CertificatesAndAwardCard
        },
        data() {
            return {
                certificatesAndAwardCardArray: [{
                    school:"freeCodeCamp",
                    course:"Responsive Web Design",
                    dates:"Dec 2021 - Feb 2022",
                    image:"ResponsiveWebIcon.svg",
                    widthOfSVG:"43.5px",
                    heightOfSVG:"43.5px",
                }, {
                    school:"Google",
                    course:"Data Strcture & Algorithms",
                    dates:"Mar 2021 - Jun 2021",
                    image:"GoogleIconS.svg",
                    widthOfSVG:"47.4px",
                    heightOfSVG:"47.4px"
                }]
            }
        },
        mounted() {
            for (let i = 0; i < this.certificatesAndAwardCardArray.length; i += 1) {
                if (i === 0) {
                    this.certificatesAndAwardCardArray[i].radius = "5px 5px 0px 0px"
                }
                if (i !== 0 && i !== this.certificatesAndAwardCardArray.length - 1) {
                    this.certificatesAndAwardCardArray[i].radius = "0px 0px 0px 0px"
                }
                if (i === this.certificatesAndAwardCardArray.length - 1) {
                    this.certificatesAndAwardCardArray[i].radius = "0px 0px 5px 5px"
                }
            }
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