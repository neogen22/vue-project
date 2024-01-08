<template>
    <div class="certificates-and-award-complex-card-wrapper">
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
                certificatesAndAwardCardArray: [
                    {
                        school:"freeCodeCamp",
                        course:"Responsive Web Design",
                        dates:"Dec 2021 - Feb 2022",
                        image:"ResponsiveWebIcon.svg",
                        widthOfSVG:"44px",
                        heightOfSVG:"44px",
                    }, 
                    {
                        school:"Google",
                        course:"Data Strcture & Algorithms",
                        dates:"Mar 2021 - Jun 2021",
                        image:"GoogleIconS.svg",
                        widthOfSVG:"47px",
                        heightOfSVG:"47px"
                    }
                ]
            }
        },
        beforeMount() {
            for (let i = 0; i < this.certificatesAndAwardCardArray.length; i += 1) {
                this.certificatesAndAwardCardArray[i].id = `${i}${this.certificatesAndAwardCardArray[i].school}`
            }
        },
        mounted() {
            this.certificatesAndAwardCardArray[0].radius = "10px 10px 0px 0px"
            this.certificatesAndAwardCardArray[this.certificatesAndAwardCardArray.length - 1].radius = "0px 0px 10px 10px"
        }
    }
</script>

<style scoped>
    @media screen and (min-width: 1190px) {
        .certificates-and-award-complex-card-wrapper{
            display: grid;
            column-gap: 8px;
            row-gap: 8px;                
            box-sizing: border-box;
        }
    }    
    @media screen and (min-width: 950px) and (max-width: 1189px)  {
        .certificates-and-award-complex-card-wrapper {
            display: grid;
            column-gap: 8px;
            row-gap: 8px;                        
            box-sizing: border-box;
        }
    }
    @media screen and (min-width: 300px) and (max-width: 949px)  {
        .certificates-and-award-complex-card-wrapper  {
            display: grid;
            column-gap: 8px;
            row-gap: 8px;
            box-sizing: border-box;
        }
    }    
</style>