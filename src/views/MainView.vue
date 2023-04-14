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

    labels: ['Test 1',
        'Test 2',
        'Test 3',
        'Test 4',
        'Test 5',
      ],
      value: [
        200,
        675,
        410,
        390,
        310,
      ],
    selectedView: 'Phone Operator',
    loggedIn: false,
    drawer: true,
    takingTest: false,
    openTestDialog: false,
    logoutDialog: false,
    items: [
      { title: 'Phone Operator', icon: 'mdi-phone' },
      { title: 'Intake', icon: 'mdi-sale' },
      { title: 'Sign-Up', icon: 'mdi-content-save' },
      { title: 'Cliente Service Cordinator (CSC)', icon: 'mdi-progress-check' }
    ],
    items2: [
      { title: 'Profile', icon: 'mdi-account' },
      { title: 'Logout', icon: 'mdi-logout' },
    ],
    e6: [],
        e7: [],
        states: [
          'Alabama', 'Alaska', 'American Samoa', 'Arizona',
          'Arkansas', 'California', 'Colorado', 'Connecticut',
          'Delaware', 'District of Columbia', 'Federated States of Micronesia',
          'Florida', 'Georgia', 'Guam', 'Hawaii', 'Idaho',
          'Illinois', 'Indiana', 'Iowa', 'Kansas', 'Kentucky',
          'Louisiana', 'Maine', 'Marshall Islands', 'Maryland',
          'Massachusetts', 'Michigan', 'Minnesota', 'Mississippi',
          'Missouri', 'Montana', 'Nebraska', 'Nevada',
          'New Hampshire', 'New Jersey', 'New Mexico', 'New York',
          'North Carolina', 'North Dakota', 'Northern Mariana Islands', 'Ohio',
          'Oklahoma', 'Oregon', 'Palau', 'Pennsylvania', 'Puerto Rico',
          'Rhode Island', 'South Carolina', 'South Dakota', 'Tennessee',
          'Texas', 'Utah', 'Vermont', 'Virgin Island', 'Virginia',
          'Washington', 'West Virginia', 'Wisconsin', 'Wyoming',
        ],
        example: [
          'Answer 1', 'Answer 2', 'Answer 3'
        ],

      
  }),

  methods: {
    closeDialog(){
      this.drawer = false;
    },

    downItem(title){
      if (title == 'Logout') {
        this.logoutDialog = true;
      } else {
        this.selectedView = title; 
        this.takingTest = false; 
      }
    }
  },

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
