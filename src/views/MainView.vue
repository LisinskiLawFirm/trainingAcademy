<template>
  <div>
    <navigation-bar-component></navigation-bar-component>
    
    <div @click="closeDialog">
      <div v-if="selectedView == 'Profile' && takingTest==false" style="margin:20px;">
        <v-expansion-panels>

          <v-expansion-panel>
            <v-expansion-panel-header style="font-weight: bold;">
              Phone Operator
            </v-expansion-panel-header>
            <v-expansion-panel-content>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
              <br>
              <v-sparkline
                style="margin-left:100px; margin-right: 100px;"
                :labels="labels"
                :value="value"
                color="primary"
                line-width="2"
                padding="16"
                height="50"
              ></v-sparkline>
            </v-expansion-panel-content>
        </v-expansion-panel>

        <v-expansion-panel>
            <v-expansion-panel-header style="font-weight: bold;">
              Intake
            </v-expansion-panel-header>
            <v-expansion-panel-content>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
              <br>
              <v-sparkline
                style="margin-left:100px; margin-right: 100px;"
                :labels="labels"
                :value="value"
                color="primary"
                line-width="2"
                padding="16"
                height="50"
              ></v-sparkline>
            </v-expansion-panel-content>
        </v-expansion-panel>
      
        </v-expansion-panels>
      
      </div>


      <div v-if="selectedView!='Profile' && selectedView!='Logout' && takingTest==false" style="margin:20px;">
        <h2>{{selectedView}}</h2>
        <br>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
        <br><br>
        <v-expansion-panels>
          <v-expansion-panel>
            <v-expansion-panel-header style="font-weight: bold;">
              First content
            </v-expansion-panel-header>
            <v-expansion-panel-content>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
              <br><br>
              <video src="http://iandevlin.github.io/mdn/video-player/video/tears-of-steel-battle-clip-medium.mp4" id="video-container" width="70%" controls></video>
              <br><br>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
              <br><br>
              <v-img
                height="250"
                width="400"
                src="https://picsum.photos/id/11/500/300"
              ></v-img>
              <br>
              <v-btn color="primary" @click="takingTest = true">
                Take test
              </v-btn>
            </v-expansion-panel-content>
          </v-expansion-panel>

          <v-expansion-panel>
            <v-expansion-panel-header style="font-weight: bold;">
              Second content
            </v-expansion-panel-header>
            <v-expansion-panel-content>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
              <br><br>
              <video src="http://iandevlin.github.io/mdn/video-player/video/tears-of-steel-battle-clip-medium.mp4" id="video-container" width="70%" controls></video>
              <br><br>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
              <br><br>
              <v-img
                height="250"
                width="400"
                src="https://picsum.photos/id/11/500/300"
              ></v-img>
              <br>
              <v-btn color="primary">
                Take test
              </v-btn>
            </v-expansion-panel-content>
          </v-expansion-panel>

          <v-expansion-panel>
            <v-expansion-panel-header style="font-weight: bold;">
              Third content
            </v-expansion-panel-header>
            <v-expansion-panel-content>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
              <br><br>
              <iframe height="400" src="https://docs.google.com/viewerng/viewer?url=http://infolab.stanford.edu/pub/papers/google.pdf&embedded=true" frameborder="0" width="100%"></iframe>            
            </v-expansion-panel-content>
          </v-expansion-panel>
        </v-expansion-panels>
      </div>

      <div v-if="takingTest" style="margin:20px;">   
        <h2>Test 1</h2>
        <br>
        <label>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
        </label> 
        <br><br>
        <v-divider></v-divider>
        <br>
        <label>
          <strong>QUESTION 1: </strong>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
        </label> 
        <br><br>
        <v-select
          v-model="e6"
          :items="states"
          :menu-props="{ maxHeight: '400' }"
          label="Answer 1"
          multiple
          outlined
        ></v-select>

        <v-divider></v-divider>
        <br>
        <label>
          <strong>QUESTION 2: </strong>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
        </label> 
        <br><br>
        <v-select
          v-model="e7"
          :items="example"
          :menu-props="{ maxHeight: '400' }"
          label="Answer 2"
          outlined
        ></v-select>

        <v-divider></v-divider>
        <br>
        <label>
          <strong>QUESTION 3: </strong>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
        </label> 
        <br><br>
        <v-textarea outlined label="Answer 3">

        </v-textarea>

        <v-divider></v-divider>
        <br><br>
        <v-btn color="primary" @click="openTestDialog = true;">
          Finish test
        </v-btn>
        <br><br>
      </div>


      <v-dialog
      v-model="openTestDialog"
      width="auto"
      persistent
    >

      <v-card>
        <v-card-title>
          Test 1
        </v-card-title>
        <v-card-text>
          <br>
          <strong>Right answers: 3/9</strong>
        </v-card-text>
        <v-card-actions>
          <v-btn color="primary" @click="takingTest = false; openTestDialog = false">Finish test</v-btn>
          <v-btn color="primary" @click="takingTest = true; openTestDialog = false">Retry test</v-btn>
        </v-card-actions>
        <br>
      </v-card>
    </v-dialog>

    <v-dialog
      v-model="logoutDialog"
      width="auto"
      persistent
    >

      <v-card>
        <br>
        <v-card-actions>
          <v-btn color="primary">Logout</v-btn>
          <v-btn color="primary" @click="logoutDialog = false; selectedView = 'Phone Operator'">Stay</v-btn>
        </v-card-actions>
        <br>
      </v-card>
    </v-dialog>

    </div>


  </div>
</template>

<script>

import NavigationBarComponent from '@/components/NavigationBarComponent.vue';

export default {
  name: 'MainView',
  components: {
    NavigationBarComponent,
  },
  data: () => ({
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
