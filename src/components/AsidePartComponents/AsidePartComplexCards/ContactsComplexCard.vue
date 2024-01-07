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
    @media (orientation: portrait) {
        .contact-complex-card-wrapper>div:last-child {
            padding-bottom: 4vh;
        }
        .contact-complex-card-wrapper>div {
            padding-bottom: 3vh;
        }
    }
    @media (orientation: landscape) {
        .contact-complex-card-wrapper>div  {
            padding-bottom: 24px;
        }
        .contact-complex-card-wrapper>div:last-child  {
            padding-bottom: 32px;
        }
    }
</style>