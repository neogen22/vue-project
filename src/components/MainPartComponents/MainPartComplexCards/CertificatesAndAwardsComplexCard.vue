<template>
    <div class="certificates-and-award-complex-card-wrapper" ref="certificatesRef">
        <div v-for="item in certificatesAndAwardCardArray" :key="item">
            <CertificatesAndAwardCard
                :school="item.school"
                :course="item.course"
                :dates="item.dates"
                :image="item.image"
                :widthOfSVG="item.widthOfSVG"
                :heightOfSVG="item.heightOfSVG"                
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
                reacted: 0,
                firstElement: '0px 0px 0px 0px',
                lastElement: '0px 0px 0px 0px',
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
        methods: {
            changeAngle() {
                let lengthOfTheCertificatesArray = document.querySelectorAll('.certificates-and-awards-card').length
                if (lengthOfTheCertificatesArray === 1) {
                    this.lastElement="0px 0px 20px 20px"
                } else {
                    this.firstElement="20px 20px 0px 0px"
                    this.lastElement="0px 0px 20px 20px"
                }
            }
        },
        watch: {
            reacted() {
                this.changeAngle()
            }
        },
        beforeMount() {
            for (let i = 0; i < this.certificatesAndAwardCardArray.length; i += 1) {
                this.certificatesAndAwardCardArray[i].id = `${i}${this.certificatesAndAwardCardArray[i].school}`
            }
        },        
        mounted() {
            this.changeAngle()
            const certificatesObserver = new MutationObserver(() => {
                this.reacted += 1
            })
            certificatesObserver.observe(this.$refs.certificatesRef, {childList: true})
        }
    }
</script>

<style scoped>
    .certificates-and-award-complex-card-wrapper {
        display: grid;
        column-gap: 8px;
        row-gap: 8px;
        box-sizing: border-box;
    }
    .certificates-and-award-complex-card-wrapper div:first-child > div  {
        border-radius: v-bind('firstElement');
    }
    .certificates-and-award-complex-card-wrapper div:last-child > div {
        border-radius: v-bind('lastElement');
    }
</style>