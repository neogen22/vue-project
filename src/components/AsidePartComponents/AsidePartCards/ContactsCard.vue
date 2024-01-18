<template>
    <div class="contacts-card-wrapper">
        <img :src="imageURL" alt="">
        <div class="contacts-card-wrapper-inside">
            <span class="contacts-card-type-of-address">{{ type }}</span>
            <span v-if="type==='Address'" class="contacts-card-address">{{ address }}</span>
            <a v-else :href="checkHref" class="contacts-card-address" :style="{textDecoration: decoration}" :type='type'>{{ address }}</a>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        image: {
            type: String,
            required: true,
        },
        type: {
            type: String,
            required: false,
        },
        address: {
            type: String,
            required: true,
        },
        decoration: {
            type: String,
            required: false,
        },
    },
    data() {
        return {            
            imageURL: new URL(`/public/${this.image}`, import.meta.url),
        }
    },
    computed: {        
        checkHref() {
            switch(this.type) {
                case 'Email':
                    return `mailto:${this.address}`
                case 'Website':
                    return `${this.address.replaceAll(' ', '')}`
                case 'Phone':
                    return `tel:${this.address.replaceAll(' ', '')}`
                default:
                    return 'PostAddress'
                }
            }
        },
    }
</script>

<style scoped>
    a {
        text-decoration: none;
        padding: 0;
        margin: 0;
        color: var(--gray-dark);
        font-family: 'DM Sans', sans-serif;
        font-size: 14px;
        font-style: normal;
        font-weight: 500;
        line-height: 1.29;
    }
    img {
        align-self: center;
        width: 32px;
        height: 32px;
    }
    .contacts-card-address {
        color: var(--gray-dark);
        font-family: 'DM Sans', sans-serif;
        font-size: 14px;
        font-style: normal;
        font-weight: 500;
        line-height: 1.29;
    }
    .contacts-card-type-of-address {
        color: var(--gray-default, #79819A);
        font-family: 'DM Sans', sans-serif;
        font-size: 12px;
        font-style: normal;
        font-weight: 400;
        line-height: 1.33;
    }
    .contacts-card-wrapper {
        display: flex; 
        column-gap: 16px;
    }
    .contacts-card-wrapper-inside {
        display: flex;
        flex-direction: column; 
        row-gap: 2px; 
        line-height: 8px;
    }
</style>