<template>    
    <div class="contact-complex-card-wrapper">
        <div v-for="item in contactCardsArray" :key="item.id" >
            <ContactsCard 
                :image="item.image" 
                :type="item.type" 
                :address="item.address" 
                :decoration="item.decoration"
            />
        </div>
    </div>
</template>

<script>
import ContactsCard from '../AsidePartCards/ContactsCard.vue';
export default {
    components: {
        ContactsCard
    },
    data() {
        return {
            contactCardsArray: [
                {
                    image:"EmailIcon.svg",
                    type:"Email",
                    address:"anuragyadavmnp@gmail.com",
                },
                {
                    image:"ScrepkaIcon.svg",
                    type:"Website", 
                    address:"https://anuragyadav365.github.io/ portfolio.html", 
                    decoration:"underline",
                },
                {
                    image:"PhoneIcon.svg",
                    type:"Phone", 
                    address:"(+91) 981 5533 309",
                },
                {
                    image:"AddressIcon.svg", 
                    type:"Address", 
                    address:"Hallomajra, Chandigarh, India"
                }
            ]
        }
    },
}
</script>

<style scoped>
    @media screen and (max-width: 1190px) {
        .contact-complex-card-wrapper > div  {
            padding-bottom: 25px;
        }
        .contact-complex-card-wrapper > div:last-child  {
            padding-bottom: 22px;
        }
    }
    @media screen and (min-width: 1190px) {
        .contact-complex-card-wrapper > div  {
            padding-bottom: 24px;
        }
        .contact-complex-card-wrapper > div:last-child  {
            padding-bottom: 32px;
        }
    }
    @media screen and (max-width: 800px) and (min-width: 650px) {
        .contact-complex-card-wrapper {
            padding-top: 10px;
            display: grid;
            grid-template-columns: 260px 260px;
        }
        .contact-complex-card-wrapper>div {
            padding-bottom: 10px;
        }
    }
    @media screen and (max-width: 650px) {
        .contact-complex-card-wrapper {
            display: flex;
            flex-direction: column;
            width: 300px;
            margin-left: auto;
            margin-right: auto;
        }
    }
</style>