<template>
  <div>
    <v-snackbar timeout='1500' color='#C5B47E' rounded='pill' v-model='controlVariables.coppiedToClipboardSnackbar' v-if='controlVariables.currentLanguage == "ENG"'>Notes coppied to clipboard</v-snackbar>
    <v-snackbar timeout='1500' color='#C5B47E' rounded='pill' v-model='controlVariables.coppiedToClipboardSnackbar' v-else>Notas copiadas al portapapeles</v-snackbar>

    <h2 class='categoryNameLabel'>Intake</h2>
    <br>
    <v-expansion-panels>

      <v-expansion-panel>
        <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Day 1</v-expansion-panel-header>
        <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Día 1</v-expansion-panel-header>
        <v-expansion-panel-content>
          
          <label class='expansionPanelContentLabel' v-if='controlVariables.currentLanguage == "ENG"'>Welcome to your first day of training as part of the Intake Team! To get started, you'll want to watch these informative videos about the initial steps we take here at the firm. Good luck!</label>
          <label class='expansionPanelContentLabel' v-else>¡Bienvenido a tu primer día de entrenamiento como parte del Intake Team! Para comenzar, deberás ver estos vídeos informativos sobre los pasos iniciales que realizamos aquí en la firma. ¡Buena suerte!</label>
          <br><br>

          <v-expansion-panels>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Family based petitions</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Peticiones basadas en la familia</v-expansion-panel-header>
              <v-expansion-panel-content>
                <div class='videoAndNotesContainer'>
                  <div class='videoContainer'>
                    <video width='640' height='400' controls='controls'>
                      <source src='https://www.dropbox.com/s/b18yun8pzwfotox/4.%20Family%20Based%20Petitions.mp4?raw=1' type='video/mp4'/>
                    </video>
                  </div>
                  <div class='notesContainer'>
                    <v-textarea class='notesInput' height='400' color='#C5B47E' append-icon='mdi-content-copy' v-model='userInputs.familyBasedPetitionsNotesInput' @click:append='copyToClipboard(userInputs.familyBasedPetitionsNotesInput)' outlined no-resize></v-textarea>
                  </div>
                </div>
              </v-expansion-panel-content>
            </v-expansion-panel>  
            
            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Consular processing</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Trámites consulares</v-expansion-panel-header>
              <v-expansion-panel-content>
                <div class='videoAndNotesContainer'>
                  <div class='videoContainer'>
                    <video width='640' height='400' controls='controls'>
                      <source src='https://www.dropbox.com/s/gvl12lwe769ve59/6.%20Consular%20Processing.mp4?raw=1' type='video/mp4'/>
                    </video>
                  </div>
                  <div class='notesContainer'>
                    <v-textarea class='notesInput' height='400' color='#C5B47E' append-icon='mdi-content-copy' v-model='userInputs.consularProcessingNotesInput' @click:append='copyToClipboard(userInputs.consularProcessingNotesInput)' outlined no-resize></v-textarea>
                  </div>
                </div>
              </v-expansion-panel-content>
            </v-expansion-panel>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Training with Angel Attorney (I)</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Entrenamiento con la Abogada Angel (I)</v-expansion-panel-header>
              <v-expansion-panel-content>
                <div class='videoAndNotesContainer'>
                  <div class='videoContainer'>
                    <video width='640' height='400' controls='controls'>
                      <source src='https://www.dropbox.com/s/dmzvz9pxwtsh0gt/Training%20Angel%20I-130_I-601_CP_AOS%20%28approved%20I-130%29-.mp4?raw=1' type='video/mp4'/>
                    </video>
                  </div>
                  <div class='notesContainer'>
                    <v-textarea class='notesInput' height='400' color='#C5B47E' append-icon='mdi-content-copy' v-model='userInputs.trainingWithAngelAttorneyINotesInput' @click:append='copyToClipboard(userInputs.trainingWithAngelAttorneyINotesInput)' outlined no-resize></v-textarea>
                  </div>
                </div>
              </v-expansion-panel-content>
            </v-expansion-panel>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Training with Rea (I)</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Entrenamiento Rea (I)</v-expansion-panel-header>
              <v-expansion-panel-content>
                <div class='videoAndNotesContainer'>
                  <div class='videoContainer'>
                    <video width='640' height='400' controls='controls'>
                      <source src='https://www.dropbox.com/s/suiuawi7jbtr1y9/Intake%20Team%20Training%20Rea%20I-130.mp4?raw=1' type='video/mp4'/>
                    </video>
                  </div>
                  <div class='notesContainer'>
                    <v-textarea class='notesInput' height='400' color='#C5B47E' append-icon='mdi-content-copy' v-model='userInputs.trainingWithReaINotesInput' @click:append='copyToClipboard(userInputs.trainingWithReaINotesInput)' outlined no-resize></v-textarea>
                  </div>
                </div>
              </v-expansion-panel-content>
            </v-expansion-panel>
            

          </v-expansion-panels>
          
          

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
</template>
  
<style scoped> 
  .categoryNameLabel{
    user-select: none;
  }
  .expansionPanelHeaderLabel{
    font-weight: bold;
  }
  .expansionPanelContentLabel{
    user-select: none;
  }
  .videoAndNotesContainer{
    display: flex;
  }
  .videoContainer{
    width: 60%;
  }
  .notesContainer{
    width: 40%;
    max-height: 400px;
  }
  .notesInput{
  }

</style>
  
<script>
  export default {
    name: 'IntakeTeamComponent',

    data: () => 
    ({
      controlVariables: 
      {
        currentLanguage: '',
        coppiedToClipboardSnackbar: false
      },

      userInputs:
      {
        familyBasedPetitionsNotesInput: '',
        consularProcessingNotesInput: '',
        trainingWithAngelAttorneyINotesInput: '',
        trainingWithReaINotesInput: '',
      }
    }),

    methods: {
      copyToClipboard(notesInput){
        var temporalComponent = document.createElement('textarea');
        document.body.appendChild(temporalComponent);
        temporalComponent.value = notesInput;
        temporalComponent.select();
        document.execCommand('copy');
        document.body.removeChild(temporalComponent);
        this.controlVariables.coppiedToClipboardSnackbar = true;
      }
    },

    created(){
      this.controlVariables.currentLanguage = 'ENG';
    },

    mounted: function () { 
      this.$root.$on('switchLanguage', (newLanguage) => {
        this.controlVariables.currentLanguage = newLanguage;
      })
    }
  }
</script>