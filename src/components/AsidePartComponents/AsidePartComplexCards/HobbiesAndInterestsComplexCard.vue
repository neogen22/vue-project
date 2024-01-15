<template>
    <div class="hobbies-and-interests-complex-card-wrapper" v-if="width > 800 || width < 450">
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
    <div v-else>
        <div class="header">
            <AsidePartCardHeader
                asideCardHeader="Hobbies & Interests"
            />
        </div>
        <div class="hobbies-and-interests-complex-card-wrapper-alternative">
            <div v-for="item in hobbiesAndInterestsCardsArray" :key="item.id">
                <HobbiesAndInterestsCard
                    :name="item.name"
                    :image="item.image"
                />
            </div>
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
        .header {
            margin-top: 30px;
            margin-left: 200px;
        }
        .hobbies-and-interests-complex-card-wrapper-alternative {
            padding-top: 10px;
            display: grid;
            grid-template-columns: 160px 160px 160px;
        }        
        .hobbies-and-interests-complex-card-wrapper-alternative div {
            padding-bottom: 10px;
        }
    }
</style>