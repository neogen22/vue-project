<template>
  <div class="main-part-wrapper">
      <div class="main-part-wrapper-inside">
        <MainPartLine/>
        <div>            
          <HeaderOfMainPart header="Education"/>
          <EducationComplexCard/>
        </div>
      </div>
      <div class="main-part-wrapper-inside">
        <MainPartLine/>
        <div>
          <HeaderOfMainPart header="Achievements"/>
          <AchievementsComplexCardWithLine/>
        </div>
      </div>
      <div class="main-part-wrapper-inside">
        <MainPartLine/>
        <div>
          <HeaderOfMainPart header="Tools/Skills"/>
          <ToolsAndSkillsComplexCard/>
        </div>
      </div>
      <div class="main-part-wrapper-inside">
        <MainPartLine/>
        <div>
          <HeaderOfMainPart header="Latest projects"/>
          <LatestProjectsComplexCard/>
        </div>
      </div>
      <div class="main-part-wrapper-inside">
        <MainPartLine/>
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
import AchievementsComplexCardWithLine from './MainPartComplexCards/AchievementsComplexCardWithLine.vue';
import ToolsAndSkillsComplexCard from './MainPartComplexCards/ToolsAndSkillsComplexCard.vue';
import LatestProjectsComplexCard from './MainPartComplexCards/LatestProjectComplexCard.vue'
import CertificatesAndAwardsComplexCard from './MainPartComplexCards/CertificatesAndAwardsComplexCard.vue'
import MainPartLine from './MainPartLine.vue'

export default {
  components: {
    EducationComplexCard,
    HeaderOfMainPart,    
    AchievementsComplexCardWithLine,
    ToolsAndSkillsComplexCard,
    LatestProjectsComplexCard,
    CertificatesAndAwardsComplexCard,    
    MainPartLine
  },
}  
</script>

<style scoped>
    @media screen and (min-width: 950px) {
      .main-part-wrapper {
        display: flex;
        flex-direction: column;
        column-gap: 16px;
        padding: 65px 48px 65px 42px;
        width: 550px;
      }
      .main-part-wrapper-inside {
        display: flex;
        flex-direction: row;
        column-gap: 16px;
      }
    }
    @media screen and (min-width: 450px) and (max-width: 950px) {
      .main-part-wrapper {
        display: flex;
        flex-direction: column;
        column-gap: 16px;
        padding: 65px 48px 65px 42px;
      }
      .main-part-wrapper-inside {
        display: flex;
        flex-direction: row;
        column-gap: 16px;
      }
    }
    @media screen and (max-width: 450px) {
      .main-part-wrapper {
        display: flex;
        flex-direction: column;
        column-gap: 16px;
        padding-top: 4vh;
      }
      .main-part-wrapper-inside {
        display: flex;
        flex-direction: row;
        column-gap: 16px;
      }
    }
</style>