<template>    
    <div class="language-complex-card-wrapper">        
        <AsidePartCardHeader 
        asideCardHeader="Languages"                
        />
        <LanguagesCard 
        language="Hindi" 
        level="Native" 
        image="India.svg"
        :paddingBottom="padding"
        />
        <LanguagesCard 
        language="English" 
        level="Professional working" 
        image="England.svg"
        :paddingBottom="padding"
        />
        <LanguagesCard 
        language="Spanish" 
        level="Elementary" 
        image="Wikipedia-Flags-ES-Spain-Flag.svg"        
        />
    </div>
</template>

<script>
    import LanguagesCard from '../AsidePartCards/LanguagesCard.vue'
    import AsidePartCardHeader from '../AsidePartCards/AsidePartCardHeader.vue'
    export default {
        components: {
            LanguagesCard,
            AsidePartCardHeader
        },
        data() {
            return {
                deviceWidth: 0,
                deviceHeight: 0,
                padding: "28px"
            }
        },
        mounted() {
            this.deviceWidth = window.innerWidth
            this.deviceHeight = window.innerHeight
            if (this.deviceHeight > this.deviceWidth) {
                this.padding = "3vh"
            }
        }
    }
</script>

<style scoped>
    @media (orientation: portrait) {
        .language-complex-card-wrapper {
            padding-bottom: 4vh
        }
    }
    @media (orientation: landscape) {
        .language-complex-card-wrapper {
            padding-bottom: 32px;
        }
    }
</style>