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
                width: undefined,
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
        created() {
            this.width = window.innerWidth
            window.addEventListener('resize', () => {
                this.width = window.innerWidth
            })
        },
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
    @media screen and (max-width: 800px) and (min-width: 450px) {
        .hobbies-and-interests-complex-card-wrapper {
            display: grid;
            grid-template-columns: 260px 260px;
        }
        .hobbies-and-interests-complex-card-wrapper div:first-child {
            grid-column: span 2;
            justify-self: center;
        }
    }
</style>