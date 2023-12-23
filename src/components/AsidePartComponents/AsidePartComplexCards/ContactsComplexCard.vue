<template>
    <div class="wrapper">
        <ContactsCard 
        image="EmailIcon.svg" 
        type="Email" 
        address="anuragyadavmnp@gmail.com"
        />
        <ContactsCard 
        image="ScrepkaIcon.svg" 
        type="Website" 
        address="https://anuragyadav365.github.io/ portfolio.html" 
        decoration="underline"
        />
        <ContactsCard 
        image="PhoneIcon.svg" 
        type="Phone" 
        address="(+91) 981 5533 309"
        />
        <ContactsCard 
        image="AddressIcon.svg" 
        type="Address" 
        address="Hallomajra, Chandigarh, India"
        paddingBottom="32.27px"
        />
    </div>    
</template>

<script>
import ContactsCard from '../AsidePartCards/ContactsCard.vue';
export default {
    components: {
        ContactsCard
    },
}
</script>

<style scoped>      
</style>