<template>
  <div>
    <language-switch-component></language-switch-component>
    <navigation-bar-component></navigation-bar-component>
    
    <div class='contentContainer'>
      <intake-team-component v-if='controlVariables.currentNavigationBarCategory == "Intake"'></intake-team-component>
    </div>

  </div>
</template>

<style scoped>
  .contentContainer{
    margin: 20px;
  }
</style>

<script>

import NavigationBarComponent from '@/components/NavigationBarComponent.vue';
import LanguageSwitchComponent from '@/components/LanguageSwitchComponent.vue';
import IntakeTeamComponent from '@/components/IntakeTeamComponent.vue';

export default {
  name: 'MainView',
  components: {
    NavigationBarComponent,
    LanguageSwitchComponent,
    IntakeTeamComponent
  },
  data: () => ({
    controlVariables: 
    {
      currentNavigationBarCategory: '',
    },      
  }),

  methods: {},

  created(){
    this.controlVariables.currentNavigationBarCategory = 'Intake';
  },

  mounted: function () { 
    this.$root.$on('openNavigationBarCategory', (newNavigationBarCategory) => {
      this.controlVariables.currentNavigationBarCategory = newNavigationBarCategory;
    })
  }
}
</script>
