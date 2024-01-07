<template>
    <div class="hobbies-and-interests-complex-card-wrapper">
        <div>
            <AsidePartCardHeader 
                asideCardHeader="Hobbies & Interests"                
            />
        </div>
        <div v-for="item in hobbiesAndInterestsCardsArray" :key="item.id">
            <HobbiesAndInterestsCard 
                :name="item.name"
                :image="item.image"
            />
        </div>
    </div>
</template>

<script>
    import HobbiesAndInterestsCard from '../AsidePartCards/HobbiesAndInterestsCard.vue'
    import AsidePartCardHeader from '../AsidePartCards/AsidePartCardHeader.vue'
    export default {
        components: {
            HobbiesAndInterestsCard,
            AsidePartCardHeader
        },
        data() {
            return {
                hobbiesAndInterestsCardsArray:[
                    {
                        name:"Gaming", 
                        image:"Play.svg"
                    },
                    {
                        name:"Traveling", 
                        image:"Earth.svg"
                    },
                    {
                        name:"Sketching/Graffitti", 
                        image:"Brush.svg"
                    },
                    {
                        name:"Blogging",
                        image:"Blogging.svg"
                    }
                ]
            }
        },        
        beforeMount() {
            for (let i = 0; i < this.hobbiesAndInterestsCardsArray.length; i += 1) {
                this.hobbiesAndInterestsCardsArray[i].id = `${i}${this.hobbiesAndInterestsCardsArray[i].name}`
            }
        },
    }
</script>

<style scoped>
    @media (orientation: portrait) {
        .hobbies-and-interests-complex-card-wrapper>div {
            padding-bottom: 3vh;
        }
        .hobbies-and-interests-complex-card-wrapper>div:last-child {
            padding-bottom: 4vh;
        }
    }
    @media (orientation: landscape) {
        .hobbies-and-interests-complex-card-wrapper>div {
            padding-bottom: 16px;
        }
        .hobbies-and-interests-complex-card-wrapper>div:last-child {
            padding-bottom: 32px;
        }
    }
</style>