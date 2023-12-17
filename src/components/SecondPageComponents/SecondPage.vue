<script>
import EducationComplexCard from './SecondPageComplexCards/EducationComplexCard.vue';
import HeaderOfSecondPage from './SecondPageComplexCards/HeaderOfSecondPage.vue';
import AchievementsComplexCard from './SecondPageComplexCards/AchievementsComplexCard.vue';
import ToolsAndSkillsComplexCard from './SecondPageComplexCards/ToolsAndSkillsComplexCard.vue';
import LatestProjectsComplexCard from './SecondPageComplexCards/LatestProjectComplexCard.vue'
import CertificatesAndAwardsComplexCard from './SecondPageComplexCards/CertificatesAndAwardsComplexCard.vue'
import CircleVue from './CircleVue.vue'

export default {
  components: {
    EducationComplexCard,
    HeaderOfSecondPage,    
    AchievementsComplexCard,
    ToolsAndSkillsComplexCard,
    LatestProjectsComplexCard,
    CertificatesAndAwardsComplexCard,
    CircleVue,
  }
}  
</script>

<template>
    <div class="wrapper-second-page">
        <div class="wrapper-second-page-inside">
          <CircleVue/>
          <div>            
            <HeaderOfSecondPage header="Education"/>
            <EducationComplexCard/>
          </div>
        </div>
        <div class="wrapper-second-page-inside">
          <CircleVue/>
          <div>
            <HeaderOfSecondPage header="Achievements"/>
            <AchievementsComplexCard/>
          </div>
        </div>
        <div class="wrapper-second-page-inside">
          <CircleVue/>
          <div>
            <HeaderOfSecondPage header="Tools/Skills"/>
            <ToolsAndSkillsComplexCard/>
          </div>
        </div>
        <div class="wrapper-second-page-inside">
          <CircleVue/>
          <div>
            <HeaderOfSecondPage header="Latest projects"/>
            <LatestProjectsComplexCard/>
          </div>
        </div>
        <div class="wrapper-second-page-inside" >
          <CircleVue/>
          <div>
            <HeaderOfSecondPage header="Certificates & Awards"/>
            <CertificatesAndAwardsComplexCard/>
          </div>
        </div>
    </div>
</template>

<style scoped>
    .wrapper-second-page {
        display: flex;
        flex-direction: column;
        width: 378px;
        height: 135px;
        column-gap: 16px;
        padding-top: 32px;
    }
    .wrapper-second-page-inside {
      display: flex; 
      flex-direction: row; 
      column-gap: 16px;
    }
</style>