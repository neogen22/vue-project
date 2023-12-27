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

<script>
import EducationComplexCard from './MainPartComplexCards/EducationComplexCard.vue';
import HeaderOfSecondPage from './MainPartComplexCards/HeaderOfSecondPage.vue';
import AchievementsComplexCard from './MainPartComplexCards/AchievementsComplexCard.vue';
import ToolsAndSkillsComplexCard from './MainPartComplexCards/ToolsAndSkillsComplexCard.vue';
import LatestProjectsComplexCard from './MainPartComplexCards/LatestProjectComplexCard.vue'
import CertificatesAndAwardsComplexCard from './MainPartComplexCards/CertificatesAndAwardsComplexCard.vue'
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

<style scoped>
    @media (orientation: portrait) {
      .wrapper-second-page {
        display: flex;
        flex-direction: column;        
        column-gap: 16px;
        padding: 0;
        margin-left: -25px
      }
      .wrapper-second-page-inside {
        display: flex;
        flex-direction: row;
        column-gap: 0px;
      }      
    }
    @media (orientation: landscape) {
      .wrapper-second-page {
        display: flex;
        flex-direction: column;        
        column-gap: 16px;
        padding: 65px 48px 65px 32px
      }
      .wrapper-second-page-inside {
        display: flex;
        flex-direction: row;
        column-gap: 16px;
      }
    }
</style>