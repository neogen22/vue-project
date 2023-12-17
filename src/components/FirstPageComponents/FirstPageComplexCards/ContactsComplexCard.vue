<template>
    <div class="wrapper">
        <ContactsCard 
        image="./src/components/icons/EmailIcon.svg" 
        type="Email" 
        address="anuragyadavmnp@gmail.com"
        />
        <ContactsCard 
        image="./src/components/icons/ScrepkaIcon.svg" 
        type="Website" 
        address="https://anuragyadav365.github.io/ portfolio.html" 
        decoration="underline"
        />
        <ContactsCard 
        image="./src/components/icons/PhoneIcon.svg" 
        type="Phone" 
        address="(+91) 981 5533 309"
        />
        <ContactsCard 
        image="./src/components/icons/AddressIcon.svg" 
        type="Address" 
        address="Hallomajra, Chandigarh, India"
        />
    </div>    
</template>

<script>
import ContactsCard from '../FirstPageCards/ContactsCard.vue';
export default {
    components: {
        ContactsCard
    },
}
</script>

<style scoped>
    .wrapper {
        display: flex;
        flex-direction: column;
        row-gap: 24.2px;
        padding-top: 32.27px;
    }    
</style>