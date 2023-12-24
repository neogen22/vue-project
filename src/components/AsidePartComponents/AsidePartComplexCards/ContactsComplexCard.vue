<template>
    <div class="contact-complex-card-wrapper">
        <ContactsCard 
        image="EmailIcon.svg" 
        type="Email" 
        address="anuragyadavmnp@gmail.com"
        :paddingBottom="padding"
        />
        <ContactsCard 
        image="ScrepkaIcon.svg" 
        type="Website" 
        address="https://anuragyadav365.github.io/ portfolio.html" 
        decoration="underline"
        :paddingBottom="padding"
        />
        <ContactsCard 
        image="PhoneIcon.svg" 
        type="Phone" 
        address="(+91) 981 5533 309"
        :paddingBottom="padding"
        />
        <ContactsCard 
        image="AddressIcon.svg" 
        type="Address" 
        address="Hallomajra, Chandigarh, India"
        />
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
            deviceWidth: 0,
            deviceHeight: 0,
            padding: "31px"
        }
    },
    mounted() {
        this.deviceWidth = window.innerWidth
        this.deviceHeight = window.innerHeight
        if (this.deviceHeight > this.deviceWidth) {
            this.padding = "5%"
        }
    }
}
</script>

<style scoped>
    @media (orientation: portrait) {
        .contact-complex-card-wrapper {
            padding-bottom: 7%
        }
    }
    @media (orientation: landscape) {
        .contact-complex-card-wrapper {
            padding-bottom: 32px;
        }
    }
</style>