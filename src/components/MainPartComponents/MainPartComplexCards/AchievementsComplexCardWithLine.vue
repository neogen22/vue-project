<template>
    <div class="achievements-complex-card-with-line-wrapper">
        <AchievementsLine />
        <div class="achievements-for-line">    
            <AchievementsComplexCard />
        </div>
    </div>    
</template>
<script>
    import AchievementsComplexCard from '../MainPartComplexCards/AchievementsComplexCard.vue'
    import AchievementsLine from '../MainPartCards/AchievementsLine.vue'
    export default {
        components: {
            AchievementsComplexCard,
            AchievementsLine
        },
    }
</script>
<style scoped>
    .achievements-complex-card-with-line-wrapper {
        margin-left: 5px;
        padding-bottom: 48px;
    }  
    .achievements-complex-card-with-line-wrapper {
        display: flex;
        flex-direction: row;
    }
    .achievements-for-line{
        margin-left: -6.8px
    }
</style>