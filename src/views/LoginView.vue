<template>
    <div style="text-align: center;">
      <h2>LLF Academyddddd</h2>
    </div>

    <br><br>

      <v-text-field
        label="Email"
        required
        outlined
      ></v-text-field>

      <v-text-field
        label="Password"
        required
        outlined
        type="password"
      ></v-text-field>

      <div class="d-flex flex-column">
        <v-btn
          color="primary"
          class="mt-4"
          block
          @click="loggedIn = true;"
        >
          Login
        </v-btn>
      </div>
  
  
</template>
  
  <script>
  
  
  export default {
    name: 'MainView',
    components: {
    },
    data: () => ({
      controlVariables:
      {
        loggedIn: true,
      },

      labels: [
          'Test 1',
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
    }
  }
  </script>
  