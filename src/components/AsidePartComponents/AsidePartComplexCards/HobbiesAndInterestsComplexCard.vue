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
        }
    }
</script>

<style scoped>
    @media screen and (max-width: 1190px) {
        .hobbies-and-interests-complex-card-wrapper>div {
            padding-bottom: 25px;
        }
        .hobbies-and-interests-complex-card-wrapper>div:last-child {
            padding-bottom: 22px;
        }
    }
    @media screen and (min-width: 1190px) {
        .hobbies-and-interests-complex-card-wrapper>div {
            padding-bottom: 16px;
        }
        .hobbies-and-interests-complex-card-wrapper>div:last-child  {
            padding-bottom: 32px;
        }
    }
    @media screen and (min-width: 650px) and (max-width: 800px) {
        .hobbies-and-interests-complex-card-wrapper {
            display: grid;
            grid-template-columns: 260px 260px;
        }
        .hobbies-and-interests-complex-card-wrapper div:first-child {
            grid-column: span 2;
            justify-self: center;
        }
    }
    @media screen and (min-width: 500px) and (max-width: 650px) {
        .hobbies-and-interests-complex-card-wrapper {
            display: grid;
            grid-template-columns: 200px 200px;
        }
        .hobbies-and-interests-complex-card-wrapper div:first-child {
            grid-column: span 2;
            justify-self: center;
        }
    }
</style>