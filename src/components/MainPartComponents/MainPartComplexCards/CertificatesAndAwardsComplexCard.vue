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
                portrait: undefined,
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
            if (window.innerHeight > window.innerWidth) {
                this.portrait = true
            } else {
                this.portrait = false
            }
            if (this.portrait) {
                if (this.certificatesAndAwardCardArray.length === 1) {
                    this.certificatesAndAwardCardArray[0].radius = '15px 15px 15px 15px'
                } else {
                    this.certificatesAndAwardCardArray[0].radius = '15px 15px 0px 0px'
                    this.certificatesAndAwardCardArray[this.certificatesAndAwardCardArray.length - 1].radius = '0px 0px 15px 15px'
                }
            } else {
                if (this.certificatesAndAwardCardArray.length === 1) {
                    this.certificatesAndAwardCardArray[0].radius = '5px 5px 5px 5px'
                } else {
                    this.certificatesAndAwardCardArray[0].radius = '5px 5px 0px 0px'
                    this.certificatesAndAwardCardArray[this.certificatesAndAwardCardArray.length - 1].radius = "0px 0px 5px 5px"
                }
            }
        },
    }
</script>

<style scoped>
    @media (orientation: portrait) {
        .certificates-and-award-complex-card-wrapper {
            display: flex; 
            flex-direction: column; 
            row-gap: 8px;
            box-sizing: border-box;
            height: auto;
        }
    }
    @media (orientation: landscape) {
        .certificates-and-award-complex-card-wrapper {
            display: flex; 
            flex-direction: column; 
            row-gap: 8px;
            box-sizing: border-box;
            padding: 0 24px;
            width: 696px; 
            height: auto;
    }
}
</style>