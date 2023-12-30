<template>
  <div class="wrapper-main-page">
      <div class="wrapper-main-page-inside">
        <CircleVue/>
        <div>            
          <HeaderOfMainPart header="Education"/>
          <EducationComplexCard/>
        </div>
      </div>
      <div class="wrapper-main-page-inside">
        <CircleVue/>
        <div>
          <HeaderOfMainPart header="Achievements"/>
          <AchievementsComplexCard/>
        </div>
      </div>
      <div class="wrapper-main-page-inside">
        <CircleVue/>
        <div>
          <HeaderOfMainPart header="Tools/Skills"/>
          <ToolsAndSkillsComplexCard/>
        </div>
      </div>
      <div class="wrapper-main-page-inside">
        <CircleVue/>
        <div>
          <HeaderOfMainPart header="Latest projects"/>
          <LatestProjectsComplexCard/>
        </div>
      </div>
      <div class="wrapper-main-page-inside" >
        <CircleVue/>
        <div>
          <HeaderOfMainPart header="Certificates & Awards"/>
          <CertificatesAndAwardsComplexCard/>
        </div>
      </div>
  </div>
</template>

<script>
import EducationComplexCard from './MainPartComplexCards/EducationComplexCard.vue';
import HeaderOfMainPart from './MainPartComplexCards/HeaderOfMainPart.vue';
import AchievementsComplexCard from './MainPartComplexCards/AchievementsComplexCard.vue';
import ToolsAndSkillsComplexCard from './MainPartComplexCards/ToolsAndSkillsComplexCard.vue';
import LatestProjectsComplexCard from './MainPartComplexCards/LatestProjectComplexCard.vue'
import CertificatesAndAwardsComplexCard from './MainPartComplexCards/CertificatesAndAwardsComplexCard.vue'
import CircleVue from './CircleVue.vue'

export default {
  components: {
    EducationComplexCard,
    HeaderOfMainPart,    
    AchievementsComplexCard,
    ToolsAndSkillsComplexCard,
    LatestProjectsComplexCard,
    CertificatesAndAwardsComplexCard,
    CircleVue,
  },
}  
</script>

<style scoped>
    @media (orientation: portrait) {
      .wrapper-main-page {
        display: flex;
        flex-direction: column;        
        column-gap: 16px;
        padding: 0;
        margin-left: -25px;
        padding-top: 3vh;
      }
      .wrapper-main-page-inside {
        display: flex;
        flex-direction: row;
        column-gap: 0px;
      }      
    }
    @media (orientation: landscape) {
      .wrapper-main-page {
        display: flex;
        flex-direction: column;        
        column-gap: 16px;
        padding: 65px 48px 65px 32px
      }
      .wrapper-main-page-inside {
        display: flex;
        flex-direction: row;
        column-gap: 16px;
      }
    }
</style>