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
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Overview of government agencies</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Resumen de las agencias gubernamentales</v-expansion-panel-header>
              <v-expansion-panel-content>
                <div class='videoAndNotesContainer'>
                  <div class='videoContainer'>
                    <video id='overviewGovernmentAgenciesVideo' width='640' height='400' controls='controls'>
                      <source src='https://www.dropbox.com/s/b18yun8pzwfotox/4.%20Family%20Based%20Petitions.mp4?raw=1' type='video/mp4'/>
                    </video>
                  </div>
                  <div class='notesContainer' v-if='controlVariables.navigationBarDialog == false'>
                    <v-textarea class='notesInput' height='400' color='#C5B47E' v-model='userInputs.overviewGovernmentAgenciesNotesInput' outlined no-resize>
                      <template slot='append'>
                        <v-icon @click='copyTimeStampToNotesInput("overviewGovernmentAgenciesVideo", "overviewGovernmentAgenciesNotesInput")' class='notesInputIcon' size='15'>mdi-timer-plus-outline</v-icon>
                        <v-icon @click='copyToClipboard(userInputs.overviewGovernmentAgenciesNotesInput)' class='notesInputIcon notesInputMidIcon' size='15'>mdi-content-copy</v-icon>
                        <v-icon @click='saveNotesInput("overviewGovernmentAgenciesNotesInput")' class='notesInputIcon' size='15'>mdi-content-save-outline</v-icon>
                      </template>
                    </v-textarea>
                  </div>
                </div>
              </v-expansion-panel-content>
            </v-expansion-panel>  

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Family based petitions</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Peticiones basadas en la familia</v-expansion-panel-header>
              <v-expansion-panel-content>
                <div class='videoAndNotesContainer'>
                  <div class='videoContainer'>
                    <video id='familyBasedPetitionsVideo' width='640' height='400' controls='controls'>
                      <source src='https://www.dropbox.com/s/b18yun8pzwfotox/4.%20Family%20Based%20Petitions.mp4?raw=1' type='video/mp4'/>
                    </video>
                  </div>
                  <div class='notesContainer' v-if='controlVariables.navigationBarDialog == false'>
                    <v-textarea class='notesInput' height='400' color='#C5B47E' v-model='userInputs.familyBasedPetitionsNotesInput' outlined no-resize>
                      <template slot='append'>
                        <v-icon @click='copyTimeStampToNotesInput("familyBasedPetitionsVideo", "familyBasedPetitionsNotesInput")' class='notesInputIcon' size='15'>mdi-timer-plus-outline</v-icon>
                        <v-icon @click='copyToClipboard(userInputs.familyBasedPetitionsNotesInput)' class='notesInputIcon notesInputMidIcon' size='15'>mdi-content-copy</v-icon>
                        <v-icon @click='saveNotesInput("familyBasedPetitionsNotesInput")' class='notesInputIcon' size='15'>mdi-content-save-outline</v-icon>
                      </template>
                    </v-textarea>
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
                    <video id='consularProcessingVideo' width='640' height='400' controls='controls'>
                      <source src='https://www.dropbox.com/s/gvl12lwe769ve59/6.%20Consular%20Processing.mp4?raw=1' type='video/mp4'/>
                    </video>
                  </div>
                  <div class='notesContainer' v-if='controlVariables.navigationBarDialog == false'>
                    <v-textarea class='notesInput' height='400' color='#C5B47E' v-model='userInputs.consularProcessingNotesInput' outlined no-resize>
                      <template slot='append'>
                        <v-icon @click='copyTimeStampToNotesInput("consularProcessingVideo", "consularProcessingNotesInput")' class='notesInputIcon' size='15'>mdi-timer-plus-outline</v-icon>
                        <v-icon @click='copyToClipboard(userInputs.consularProcessingNotesInput)' class='notesInputIcon notesInputMidIcon' size='15'>mdi-content-copy</v-icon>
                        <v-icon @click='saveNotesInput("consularProcessingNotesInput")' class='notesInputIcon' size='15'>mdi-content-save-outline</v-icon>
                      </template>
                    </v-textarea>
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
                    <video id='trainingWithAngelAttorneyIVideo' width='640' height='400' controls='controls'>
                      <source src='https://www.dropbox.com/s/dmzvz9pxwtsh0gt/Training%20Angel%20I-130_I-601_CP_AOS%20%28approved%20I-130%29-.mp4?raw=1' type='video/mp4'/>
                    </video>
                  </div>
                  <div class='notesContainer' v-if='controlVariables.navigationBarDialog == false'>
                    <v-textarea class='notesInput' height='400' color='#C5B47E' v-model='userInputs.trainingWithAngelAttorneyINotesInput' outlined no-resize>
                      <template slot='append'>
                        <v-icon @click='copyTimeStampToNotesInput("trainingWithAngelAttorneyIVideo", "trainingWithAngelAttorneyINotesInput")' class='notesInputIcon' size='15'>mdi-timer-plus-outline</v-icon>
                        <v-icon @click='copyToClipboard(userInputs.trainingWithAngelAttorneyINotesInput)' class='notesInputIcon notesInputMidIcon' size='15'>mdi-content-copy</v-icon>
                        <v-icon @click='saveNotesInput("trainingWithAngelAttorneyINotesInput")' class='notesInputIcon' size='15'>mdi-content-save-outline</v-icon>
                      </template>
                    </v-textarea>
                  </div>
                </div>
              </v-expansion-panel-content>
            </v-expansion-panel>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Training with Rea (I)</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Entrenamiento con Rea (I)</v-expansion-panel-header>
              <v-expansion-panel-content>
                <div class='videoAndNotesContainer'>
                  <div class='videoContainer'>
                    <video id='trainingWithReaIVideo' width='640' height='400' controls='controls'>
                      <source src='https://www.dropbox.com/s/suiuawi7jbtr1y9/Intake%20Team%20Training%20Rea%20I-130.mp4?raw=1' type='video/mp4'/>
                    </video>
                  </div>
                  <div class='notesContainer' v-if='controlVariables.navigationBarDialog == false'>
                    <v-textarea class='notesInput' height='400' color='#C5B47E' v-model='userInputs.trainingWithReaINotesInput' outlined no-resize>
                      <template slot='append'>
                        <v-icon @click='copyTimeStampToNotesInput("trainingWithReaIVideo", "trainingWithReaINotesInput")' class='notesInputIcon' size='15'>mdi-timer-plus-outline</v-icon>
                        <v-icon @click='copyToClipboard(userInputs.trainingWithReaINotesInput)' class='notesInputIcon notesInputMidIcon' size='15'>mdi-content-copy</v-icon>
                        <v-icon @click='saveNotesInput("trainingWithReaINotesInput")' class='notesInputIcon' size='15'>mdi-content-save-outline</v-icon>
                      </template>
                    </v-textarea>
                  </div>
                </div>
              </v-expansion-panel-content>
            </v-expansion-panel>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Humanitarian options</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Opciones humanitarias</v-expansion-panel-header>
              <v-expansion-panel-content>
                <div class='videoAndNotesContainer'>
                  <div class='videoContainer'>
                    <video id='humanitarianOptionsVideo' width='640' height='400' controls='controls'>
                      <source src='https://www.dropbox.com/s/rkvk7w2nkovsro7/7.%20Humanitarian%20Options.mp4?raw=1' type='video/mp4'/>
                    </video>
                  </div>
                  <div class='notesContainer' v-if='controlVariables.navigationBarDialog == false'>
                    <v-textarea class='notesInput' height='400' color='#C5B47E' v-model='userInputs.humanitarianOptionsNotesInput' outlined no-resize>
                      <template slot='append'>
                        <v-icon @click='copyTimeStampToNotesInput("humanitarianOptionsVideo", "humanitarianOptionsNotesInput")' class='notesInputIcon' size='15'>mdi-timer-plus-outline</v-icon>
                        <v-icon @click='copyToClipboard(userInputs.humanitarianOptionsNotesInput)' class='notesInputIcon notesInputMidIcon' size='15'>mdi-content-copy</v-icon>
                        <v-icon @click='saveNotesInput("humanitarianOptionsNotesInput")' class='notesInputIcon' size='15'>mdi-content-save-outline</v-icon>
                      </template>
                    </v-textarea>
                  </div>
                </div>
              </v-expansion-panel-content>
            </v-expansion-panel>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Additional information</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Información adicional</v-expansion-panel-header>
              <v-expansion-panel-content>
                <div class='videoAndNotesContainer'>
                  <div class='videoContainer'>
                    <video id='additionalInformationVideo' width='640' height='400' controls='controls'>
                      <source src='https://www.dropbox.com/s/22iwf766zvw92o2/11.%20Additional%20Info.mp4?raw=1' type='video/mp4'/>
                    </video>
                  </div>
                  <div class='notesContainer' v-if='controlVariables.navigationBarDialog == false'>
                    <v-textarea class='notesInput' height='400' color='#C5B47E' v-model='userInputs.additionalInformationNotesInput' outlined no-resize>
                      <template slot='append'>
                        <v-icon @click='copyTimeStampToNotesInput("additionalInformationVideo", "additionalInformationNotesInput")' class='notesInputIcon' size='15'>mdi-timer-plus-outline</v-icon>
                        <v-icon @click='copyToClipboard(userInputs.additionalInformationNotesInput)' class='notesInputIcon notesInputMidIcon' size='15'>mdi-content-copy</v-icon>
                        <v-icon @click='saveNotesInput("additionalInformationNotesInput")' class='notesInputIcon' size='15'>mdi-content-save-outline</v-icon>
                      </template>
                    </v-textarea>
                  </div>
                </div>
              </v-expansion-panel-content>
            </v-expansion-panel>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Appointment script</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Script para la entrevista</v-expansion-panel-header>
              <v-expansion-panel-content>
                <iframe height='400' width='100%' frameborder='0' src='https://res.cloudinary.com/dfionqbqe/image/upload/v1681489869/intakeAppointmentScript.pdf'></iframe>            
              </v-expansion-panel-content>
            </v-expansion-panel>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Prices script</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Script para precios</v-expansion-panel-header>
              <v-expansion-panel-content>
                <iframe height='400' width='100%' frameborder='0' src='https://res.cloudinary.com/dfionqbqe/image/upload/v1681490297/intakePriceScript.pdf'></iframe>            
              </v-expansion-panel-content>
            </v-expansion-panel>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Prices script</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Script para precios</v-expansion-panel-header>
              <v-expansion-panel-content>
                <iframe height='400' width='100%' frameborder='0' src='https://res.cloudinary.com/dfionqbqe/image/upload/v1681490297/intakePriceScript.pdf'></iframe>            
              </v-expansion-panel-content>
            </v-expansion-panel>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Prices chart</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Cuadro de precios</v-expansion-panel-header>
              <v-expansion-panel-content>
                <iframe height='400' width='100%' frameborder='0' src='https://res.cloudinary.com/dfionqbqe/image/upload/v1681490661/intakePricesChart.pdf'></iframe>            
              </v-expansion-panel-content>
            </v-expansion-panel>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel expansionPanelHeaderQuizLabel' v-if='controlVariables.currentLanguage == "ENG"' @click='openTest(1)'>Quiz (I): introduction to inmigration law</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel expansionPanelHeaderQuizLabel' v-else @click='openTest(1)'>Quiz (I): introduction a la legislación de inmigración</v-expansion-panel-header>
            </v-expansion-panel>
      
          </v-expansion-panels>
          
        </v-expansion-panel-content>
      </v-expansion-panel>

      <v-expansion-panel>
        <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Day 2</v-expansion-panel-header>
        <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Día 2</v-expansion-panel-header>
        <v-expansion-panel-content>
          
          <label class='expansionPanelContentLabel' v-if='controlVariables.currentLanguage == "ENG"'>Welcome to your second day of training as part of the Intake Team! To get started, you'll want to watch these informative videos about the initial steps we take here at the firm. Good luck!</label>
          <label class='expansionPanelContentLabel' v-else>¡Bienvenido a tu segundo día de entrenamiento como parte del Intake Team! Para comenzar, deberás ver estos vídeos informativos sobre los pasos iniciales que realizamos aquí en la firma. ¡Buena suerte!</label>
          <br><br>

          <v-expansion-panels>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Ethics training</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Entrenamiento de ética</v-expansion-panel-header>
              <v-expansion-panel-content>
                <div class='videoAndNotesContainer'>
                  <div class='videoContainer'>
                    <video id='ethicsTrainingVideo' width='640' height='400' controls='controls'>
                      <source src='https://www.dropbox.com/s/qp7ooj55jgpaz26/Fall%202022%20Ethics%20Training.mp4?raw=1' type='video/mp4'/>
                    </video>
                  </div>
                  <div class='notesContainer' v-if='controlVariables.navigationBarDialog == false'>
                    <v-textarea class='notesInput' height='400' color='#C5B47E' v-model='userInputs.ethicsTrainingNotesInput' outlined no-resize>
                      <template slot='append'>
                        <v-icon @click='copyTimeStampToNotesInput("ethicsTrainingVideo", "ethicsTrainingNotesInput")' class='notesInputIcon' size='15'>mdi-timer-plus-outline</v-icon>
                        <v-icon @click='copyToClipboard(userInputs.ethicsTrainingNotesInput)' class='notesInputIcon notesInputMidIcon' size='15'>mdi-content-copy</v-icon>
                        <v-icon @click='saveNotesInput("ethicsTrainingNotesInput")' class='notesInputIcon' size='15'>mdi-content-save-outline</v-icon>
                      </template>
                    </v-textarea>
                  </div>
                </div>
              </v-expansion-panel-content>
            </v-expansion-panel>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Consult training (I)</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Consult training (I)</v-expansion-panel-header>
              <v-expansion-panel-content>
                <div class='videoAndNotesContainer'>
                  <div class='videoContainer'>
                    <video id='consultTrainingIVideo' width='640' height='400' controls='controls'>
                      <source src='https://www.dropbox.com/s/3zece9wtx5k6g6k/1.%20INTAKE%20Training%20I%20A%20video.mp4?raw=1' type='video/mp4'/>
                    </video>
                  </div>
                  <div class='notesContainer' v-if='controlVariables.navigationBarDialog == false'>
                    <v-textarea class='notesInput' height='400' color='#C5B47E' v-model='userInputs.consultTrainingINotesInput' outlined no-resize>
                      <template slot='append'>
                        <v-icon @click='copyTimeStampToNotesInput("consultTrainingIVideo", "consultTrainingINotesInput")' class='notesInputIcon' size='15'>mdi-timer-plus-outline</v-icon>
                        <v-icon @click='copyToClipboard(userInputs.consultTrainingINotesInput)' class='notesInputIcon notesInputMidIcon' size='15'>mdi-content-copy</v-icon>
                        <v-icon @click='saveNotesInput("consultTrainingINotesInput")' class='notesInputIcon' size='15'>mdi-content-save-outline</v-icon>
                      </template>
                    </v-textarea>
                  </div>
                </div>
              </v-expansion-panel-content>
            </v-expansion-panel>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>VAWA (I)</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>VAWA (I)</v-expansion-panel-header>
              <v-expansion-panel-content>
                <div class='videoAndNotesContainer'>
                  <div class='videoContainer'>
                    <video id='VAWAIVideo' width='640' height='400' controls='controls'>
                      <source src='https://www.dropbox.com/s/kfzq8135fd5wl1m/Intake%20Team%20traning%20VAWA%20part-1%20Madison%20%26%20Rea.mp4?raw=1' type='video/mp4'/>
                    </video>
                  </div>
                  <div class='notesContainer' v-if='controlVariables.navigationBarDialog == false'>
                    <v-textarea class='notesInput' height='400' color='#C5B47E' v-model='userInputs.VAWAINotesInput' outlined no-resize>
                      <template slot='append'>
                        <v-icon @click='copyTimeStampToNotesInput("VAWAIVideo", "VAWAINotesInput")' class='notesInputIcon' size='15'>mdi-timer-plus-outline</v-icon>
                        <v-icon @click='copyToClipboard(userInputs.VAWAINotesInput)' class='notesInputIcon notesInputMidIcon' size='15'>mdi-content-copy</v-icon>
                        <v-icon @click='saveNotesInput("VAWAINotesInput")' class='notesInputIcon' size='15'>mdi-content-save-outline</v-icon>
                      </template>
                    </v-textarea>
                  </div>
                </div>
              </v-expansion-panel-content>
            </v-expansion-panel>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>T-VISA</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>T-VISA</v-expansion-panel-header>
              <v-expansion-panel-content>
                <div class='videoAndNotesContainer'>
                  <div class='videoContainer'>
                    <video id='TVISAVideo' width='640' height='400' controls='controls'>
                      <source src='https://www.dropbox.com/s/69bag3ic7fhzzbg/Intake%20Team%20Training%20T-VISA.mp4?raw=1' type='video/mp4'/>
                    </video>
                  </div>
                  <div class='notesContainer' v-if='controlVariables.navigationBarDialog == false'>
                    <v-textarea class='notesInput' height='400' color='#C5B47E' v-model='userInputs.TVISANotesInput' outlined no-resize>
                      <template slot='append'>
                        <v-icon @click='copyTimeStampToNotesInput("TVISAVideo", "TVISANotesInput")' class='notesInputIcon' size='15'>mdi-timer-plus-outline</v-icon>
                        <v-icon @click='copyToClipboard(userInputs.TVISANotesInput)' class='notesInputIcon notesInputMidIcon' size='15'>mdi-content-copy</v-icon>
                        <v-icon @click='saveNotesInput("TVISANotesInput")' class='notesInputIcon' size='15'>mdi-content-save-outline</v-icon>
                      </template>
                    </v-textarea>
                  </div>
                </div>
              </v-expansion-panel-content>
            </v-expansion-panel>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Perm bar chart</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Cuadro del perm bar</v-expansion-panel-header>
              <v-expansion-panel-content>
                <iframe height='400' width='100%' frameborder='0' src='https://res.cloudinary.com/dfionqbqe/image/upload/v1681741508/intakePermBarChart.pdf'></iframe>            
              </v-expansion-panel-content>
            </v-expansion-panel>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Perm bar (I)</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Perm bar (I)</v-expansion-panel-header>
              <v-expansion-panel-content>
                <div class='videoAndNotesContainer'>
                  <div class='videoContainer'>
                    <video id='permBarIVideo' width='640' height='400' controls='controls'>
                      <source src='https://www.dropbox.com/s/3kj38tes34s8ke4/1.%20Perm%20Bar%20Training%20I.mp4?raw=1' type='video/mp4'/>
                    </video>
                  </div>
                  <div class='notesContainer' v-if='controlVariables.navigationBarDialog == false'>
                    <v-textarea class='notesInput' height='400' color='#C5B47E' v-model='userInputs.permBarINotesInput' outlined no-resize>
                      <template slot='append'>
                        <v-icon @click='copyTimeStampToNotesInput("permBarIVideo", "permBarINotesInput")' class='notesInputIcon' size='15'>mdi-timer-plus-outline</v-icon>
                        <v-icon @click='copyToClipboard(userInputs.permBarINotesInput)' class='notesInputIcon notesInputMidIcon' size='15'>mdi-content-copy</v-icon>
                        <v-icon @click='saveNotesInput("permBarINotesInput")' class='notesInputIcon' size='15'>mdi-content-save-outline</v-icon>
                      </template>
                    </v-textarea>
                  </div>
                </div>
              </v-expansion-panel-content>
            </v-expansion-panel>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Perm bar (II)</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Perm bar (II)</v-expansion-panel-header>
              <v-expansion-panel-content>
                <div class='videoAndNotesContainer'>
                  <div class='videoContainer'>
                    <video id='permBarIIVideo' width='640' height='400' controls='controls'>
                      <source src='https://www.dropbox.com/s/4fkj4ka1cosokxu/2.%20Perm%20Bar%20Training%20II%20zoom_0.mp4?raw=1' type='video/mp4'/>
                    </video>
                  </div>
                  <div class='notesContainer' v-if='controlVariables.navigationBarDialog == false'>
                    <v-textarea class='notesInput' height='400' color='#C5B47E' v-model='userInputs.permBarIINotesInput' outlined no-resize>
                      <template slot='append'>
                        <v-icon @click='copyTimeStampToNotesInput("permBarIIVideo", "permBarIINotesInput")' class='notesInputIcon' size='15'>mdi-timer-plus-outline</v-icon>
                        <v-icon @click='copyToClipboard(userInputs.permBarIINotesInput)' class='notesInputIcon notesInputMidIcon' size='15'>mdi-content-copy</v-icon>
                        <v-icon @click='saveNotesInput("permBarIINotesInput")' class='notesInputIcon' size='15'>mdi-content-save-outline</v-icon>
                      </template>
                    </v-textarea>
                  </div>
                </div>
              </v-expansion-panel-content>
            </v-expansion-panel>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel expansionPanelHeaderQuizLabel' v-if='controlVariables.currentLanguage == "ENG"' @click='openTest(2)'>Quiz (II): VAWA, T-VISA and VISA U</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel expansionPanelHeaderQuizLabel' v-else @click='openTest(2)'>Quiz (II): VAWA, T-VISA y VISA U</v-expansion-panel-header>
            </v-expansion-panel>
            
          </v-expansion-panels>
          
        </v-expansion-panel-content>
      </v-expansion-panel>

      <v-expansion-panel>
        <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Day 3</v-expansion-panel-header>
        <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Día 3</v-expansion-panel-header>
        <v-expansion-panel-content>
          
          <label class='expansionPanelContentLabel' v-if='controlVariables.currentLanguage == "ENG"'>Welcome to your third day of training as part of the Intake Team! To get started, you'll want to watch these informative videos about the initial steps we take here at the firm. Good luck!</label>
          <label class='expansionPanelContentLabel' v-else>¡Bienvenido a tu tercer día de entrenamiento como parte del Intake Team! Para comenzar, deberás ver estos vídeos informativos sobre los pasos iniciales que realizamos aquí en la firma. ¡Buena suerte!</label>
          <br><br>

          <v-expansion-panels>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Perm bar (III)</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Perm bar (III)</v-expansion-panel-header>
              <v-expansion-panel-content>
                <div class='videoAndNotesContainer'>
                  <div class='videoContainer'>
                    <video id='permBarIIIVideo' width='640' height='400' controls='controls'>
                      <source src='https://www.dropbox.com/s/01eq0hc12j341dk/4.%20Perm%20Bar%20Training%20by%20Lily%20AxelRod.mp4?raw=1' type='video/mp4'/>
                    </video>
                  </div>
                  <div class='notesContainer' v-if='controlVariables.navigationBarDialog == false'>
                    <v-textarea class='notesInput' height='400' color='#C5B47E' v-model='userInputs.permBarIIINotesInput' outlined no-resize>
                      <template slot='append'>
                        <v-icon @click='copyTimeStampToNotesInput("permBarIIIVideo", "permBarIIINotesInput")' class='notesInputIcon' size='15'>mdi-timer-plus-outline</v-icon>
                        <v-icon @click='copyToClipboard(userInputs.permBarIIINotesInput)' class='notesInputIcon notesInputMidIcon' size='15'>mdi-content-copy</v-icon>
                        <v-icon @click='saveNotesInput("permBarIIINotesInput")' class='notesInputIcon' size='15'>mdi-content-save-outline</v-icon>
                      </template>
                    </v-textarea>
                  </div>
                </div>
              </v-expansion-panel-content>
            </v-expansion-panel>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Perm bar (IV)</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Perm bar (IV)</v-expansion-panel-header>
              <v-expansion-panel-content>
                <div class='videoAndNotesContainer'>
                  <div class='videoContainer'>
                    <video id='permBarIVVideo' width='640' height='400' controls='controls'>
                      <source src='https://www.dropbox.com/s/toxia1jkdjpr77l/3.%20Perm%20Bar%20Hypos%20with%20New%20Intake.mp4?raw=1' type='video/mp4'/>
                    </video>
                  </div>
                  <div class='notesContainer' v-if='controlVariables.navigationBarDialog == false'>
                    <v-textarea class='notesInput' height='400' color='#C5B47E' v-model='userInputs.permBarIVNotesInput' outlined no-resize>
                      <template slot='append'>
                        <v-icon @click='copyTimeStampToNotesInput("permBarIVVideo", "permBarIVNotesInput")' class='notesInputIcon' size='15'>mdi-timer-plus-outline</v-icon>
                        <v-icon @click='copyToClipboard(userInputs.permBarIVNotesInput)' class='notesInputIcon notesInputMidIcon' size='15'>mdi-content-copy</v-icon>
                        <v-icon @click='saveNotesInput("permBarIVNotesInput")' class='notesInputIcon' size='15'>mdi-content-save-outline</v-icon>
                      </template>
                    </v-textarea>
                  </div>
                </div>
              </v-expansion-panel-content>
            </v-expansion-panel>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Hypotheticals</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Hipotéticos</v-expansion-panel-header>
              <v-expansion-panel-content>
                <div class='videoAndNotesContainer'>
                  <div class='videoContainer'>
                    <video id='hypotheticalsVideo' width='640' height='400' controls='controls'>
                      <source src='https://www.dropbox.com/s/w8elu2p2tkdj9m6/6.%20Hypos%20Intake.mp4?raw=1' type='video/mp4'/>
                    </video>
                  </div>
                  <div class='notesContainer' v-if='controlVariables.navigationBarDialog == false'>
                    <v-textarea class='notesInput' height='400' color='#C5B47E' v-model='userInputs.hypotheticalsNotesInput' outlined no-resize>
                      <template slot='append'>
                        <v-icon @click='copyTimeStampToNotesInput("hypotheticalsVideo", "hypotheticalsNotesInput")' class='notesInputIcon' size='15'>mdi-timer-plus-outline</v-icon>
                        <v-icon @click='copyToClipboard(userInputs.hypotheticalsNotesInput)' class='notesInputIcon notesInputMidIcon' size='15'>mdi-content-copy</v-icon>
                        <v-icon @click='saveNotesInput("hypotheticalsNotesInput")' class='notesInputIcon' size='15'>mdi-content-save-outline</v-icon>
                      </template>
                    </v-textarea>
                  </div>
                </div>
              </v-expansion-panel-content>
            </v-expansion-panel>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Miscellaneous (I)</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Misceláneos (I)</v-expansion-panel-header>
              <v-expansion-panel-content>
                <div class='videoAndNotesContainer'>
                  <div class='videoContainer'>
                    <video id='miscellaneousIVideo' width='640' height='400' controls='controls'>
                      <source src='https://www.dropbox.com/s/w8elu2p2tkdj9m6/6.%20Hypos%20Intake.mp4?raw=1' type='video/mp4'/>
                    </video>
                  </div>
                  <div class='notesContainer' v-if='controlVariables.navigationBarDialog == false'>
                    <v-textarea class='notesInput' height='400' color='#C5B47E' v-model='userInputs.miscellaneousINotesInput' outlined no-resize>
                      <template slot='append'>
                        <v-icon @click='copyTimeStampToNotesInput("miscellaneousIVideo", "miscellaneousINotesInput")' class='notesInputIcon' size='15'>mdi-timer-plus-outline</v-icon>
                        <v-icon @click='copyToClipboard(userInputs.miscellaneousINotesInput)' class='notesInputIcon notesInputMidIcon' size='15'>mdi-content-copy</v-icon>
                        <v-icon @click='saveNotesInput("miscellaneousINotesInput")' class='notesInputIcon' size='15'>mdi-content-save-outline</v-icon>
                      </template>
                    </v-textarea>
                  </div>
                </div>
              </v-expansion-panel-content>
            </v-expansion-panel>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel expansionPanelHeaderQuizLabel' v-if='controlVariables.currentLanguage == "ENG"' @click='openTest(3)'>Quiz (III): perm bar</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel expansionPanelHeaderQuizLabel' v-else @click='openTest(3)'>Quiz (III): perm bar</v-expansion-panel-header>
            </v-expansion-panel>
            
          </v-expansion-panels>
          
        </v-expansion-panel-content>
      </v-expansion-panel>

      <v-expansion-panel>
        <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Day 4</v-expansion-panel-header>
        <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Día 4</v-expansion-panel-header>
        <v-expansion-panel-content>
          
          <label class='expansionPanelContentLabel' v-if='controlVariables.currentLanguage == "ENG"'>Welcome to your fourth day of training as part of the Intake Team! To get started, you'll want to watch these informative videos about the initial steps we take here at the firm. Good luck!</label>
          <label class='expansionPanelContentLabel' v-else>¡Bienvenido a tu cuarto día de entrenamiento como parte del Intake Team! Para comenzar, deberás ver estos vídeos informativos sobre los pasos iniciales que realizamos aquí en la firma. ¡Buena suerte!</label>
          <br><br>

          <v-expansion-panels>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Lawyer referral list</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Lista de abogados de referencia</v-expansion-panel-header>
              <v-expansion-panel-content>
                <iframe height='400' width='100%' frameborder='0' src='https://res.cloudinary.com/dfionqbqe/image/upload/v1681762432/intakeLawyerReferralList.pdf'></iframe>            
              </v-expansion-panel-content>
            </v-expansion-panel>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Miscellaneous (II)</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Misceláneos (II)</v-expansion-panel-header>
              <v-expansion-panel-content>
                <div class='videoAndNotesContainer'>
                  <div class='videoContainer'>
                    <video id='miscellaneousIIVideo' width='640' height='400' controls='controls'>
                      <source src='https://www.dropbox.com/s/l8jstoghi584z19/8.%20B%20Objections-%20Questions%20-%20Misc.mp4?raw=1' type='video/mp4'/>
                    </video>
                  </div>
                  <div class='notesContainer' v-if='controlVariables.navigationBarDialog == false'>
                    <v-textarea class='notesInput' height='400' color='#C5B47E' v-model='userInputs.miscellaneousIINotesInput' outlined no-resize>
                      <template slot='append'>
                        <v-icon @click='copyTimeStampToNotesInput("miscellaneousIIVideo", "miscellaneousIINotesInput")' class='notesInputIcon' size='15'>mdi-timer-plus-outline</v-icon>
                        <v-icon @click='copyToClipboard(userInputs.miscellaneousIINotesInput)' class='notesInputIcon notesInputMidIcon' size='15'>mdi-content-copy</v-icon>
                        <v-icon @click='saveNotesInput("miscellaneousIINotesInput")' class='notesInputIcon' size='15'>mdi-content-save-outline</v-icon>
                      </template>
                    </v-textarea>
                  </div>
                </div>
              </v-expansion-panel-content>
            </v-expansion-panel>  

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Perm bar (V)</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Perm bar (V)</v-expansion-panel-header>
              <v-expansion-panel-content>
                <div class='videoAndNotesContainer'>
                  <div class='videoContainer'>
                    <video id='permBarVVideo' width='640' height='400' controls='controls'>
                      <source src='https://www.dropbox.com/s/79uhbar9okw3mzj/3.%20Perm%20Bar%20and%20Script.mp4?raw=1' type='video/mp4'/>
                    </video>
                  </div>
                  <div class='notesContainer' v-if='controlVariables.navigationBarDialog == false'>
                    <v-textarea class='notesInput' height='400' color='#C5B47E' v-model='userInputs.permBarVNotesInput' outlined no-resize>
                      <template slot='append'>
                        <v-icon @click='copyTimeStampToNotesInput("permBarVVideo", "permBarVNotesInput")' class='notesInputIcon' size='15'>mdi-timer-plus-outline</v-icon>
                        <v-icon @click='copyToClipboard(userInputs.permBarVNotesInput)' class='notesInputIcon notesInputMidIcon' size='15'>mdi-content-copy</v-icon>
                        <v-icon @click='saveNotesInput("permBarVNotesInput")' class='notesInputIcon' size='15'>mdi-content-save-outline</v-icon>
                      </template>
                    </v-textarea>
                  </div>
                </div>
              </v-expansion-panel-content>
            </v-expansion-panel>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Waivers 601 and 212</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Excepciones 601 y 212</v-expansion-panel-header>
              <v-expansion-panel-content>
                <div class='videoAndNotesContainer'>
                  <div class='videoContainer'>
                    <video id='waiversVideo' width='640' height='400' controls='controls'>
                      <source src='https://www.dropbox.com/s/ogb56ksqs132wn6/8.%20Waivers%20601%20and%20212%20All%20Firm%20Training.mp4?raw=1' type='video/mp4'/>
                    </video>
                  </div>
                  <div class='notesContainer' v-if='controlVariables.navigationBarDialog == false'>
                    <v-textarea class='notesInput' height='400' color='#C5B47E' v-model='userInputs.waiversNotesInput' outlined no-resize>
                      <template slot='append'>
                        <v-icon @click='copyTimeStampToNotesInput("waiversVideo", "waiversNotesInput")' class='notesInputIcon' size='15'>mdi-timer-plus-outline</v-icon>
                        <v-icon @click='copyToClipboard(userInputs.waiversNotesInput)' class='notesInputIcon notesInputMidIcon' size='15'>mdi-content-copy</v-icon>
                        <v-icon @click='saveNotesInput("waiversNotesInput")' class='notesInputIcon' size='15'>mdi-content-save-outline</v-icon>
                      </template>
                    </v-textarea>
                  </div>
                </div>
              </v-expansion-panel-content>
            </v-expansion-panel>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Crimes to know</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Delitos que hay que conocer</v-expansion-panel-header>
              <v-expansion-panel-content>
                <div class='videoAndNotesContainer'>
                  <div class='videoContainer'>
                    <video id='crimesVideo' width='640' height='400' controls='controls'>
                      <source src='https://www.dropbox.com/s/mm6rmaf64ia4cfb/2.%20Crimes%20To%20Know%20Plus%20Misc%20Quest.mp4?raw=1' type='video/mp4'/>
                    </video>
                  </div>
                  <div class='notesContainer' v-if='controlVariables.navigationBarDialog == false'>
                    <v-textarea class='notesInput' height='400' color='#C5B47E' v-model='userInputs.crimesNotesInput' outlined no-resize>
                      <template slot='append'>
                        <v-icon @click='copyTimeStampToNotesInput("crimesVideo", "crimesNotesInput")' class='notesInputIcon' size='15'>mdi-timer-plus-outline</v-icon>
                        <v-icon @click='copyToClipboard(userInputs.crimesNotesInput)' class='notesInputIcon notesInputMidIcon' size='15'>mdi-content-copy</v-icon>
                        <v-icon @click='saveNotesInput("crimesNotesInput")' class='notesInputIcon' size='15'>mdi-content-save-outline</v-icon>
                      </template>
                    </v-textarea>
                  </div>
                </div>
              </v-expansion-panel-content>
            </v-expansion-panel>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>NATZ</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>NATZ</v-expansion-panel-header>
              <v-expansion-panel-content>
                <div class='videoAndNotesContainer'>
                  <div class='videoContainer'>
                    <video id='NATZVideo' width='640' height='400' controls='controls'>
                      <source src='https://www.dropbox.com/s/8kvntnjr3uroc45/Intake%20Team%20Training%20NATZ.mp4?raw=1' type='video/mp4'/>
                    </video>
                  </div>
                  <div class='notesContainer' v-if='controlVariables.navigationBarDialog == false'>
                    <v-textarea class='notesInput' height='400' color='#C5B47E' v-model='userInputs.NATZNotesInput' outlined no-resize>
                      <template slot='append'>
                        <v-icon @click='copyTimeStampToNotesInput("NATZVideo", "NATZNotesInput")' class='notesInputIcon' size='15'>mdi-timer-plus-outline</v-icon>
                        <v-icon @click='copyToClipboard(userInputs.NATZNotesInput)' class='notesInputIcon notesInputMidIcon' size='15'>mdi-content-copy</v-icon>
                        <v-icon @click='saveNotesInput("NATZNotesInput")' class='notesInputIcon' size='15'>mdi-content-save-outline</v-icon>
                      </template>
                    </v-textarea>
                  </div>
                </div>
              </v-expansion-panel-content>
            </v-expansion-panel>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel expansionPanelHeaderQuizLabel' v-if='controlVariables.currentLanguage == "ENG"' @click='openTest(4)'>Quiz (IV): waivers and crimes</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel expansionPanelHeaderQuizLabel' v-else @click='openTest(4)'>Quiz (IV): excepciones y delitos</v-expansion-panel-header>
            </v-expansion-panel>

          </v-expansion-panels>
          
        </v-expansion-panel-content>
      </v-expansion-panel>

      <v-expansion-panel>
        <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Day 5</v-expansion-panel-header>
        <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Día 5</v-expansion-panel-header>
        <v-expansion-panel-content>
          
          <label class='expansionPanelContentLabel' v-if='controlVariables.currentLanguage == "ENG"'>Welcome to your fifth day of training as part of the Intake Team! To get started, you'll want to watch these informative videos about the initial steps we take here at the firm. Good luck!</label>
          <label class='expansionPanelContentLabel' v-else>¡Bienvenido a tu quinto día de entrenamiento como parte del Intake Team! Para comenzar, deberás ver estos vídeos informativos sobre los pasos iniciales que realizamos aquí en la firma. ¡Buena suerte!</label>
          <br><br>

          <v-expansion-panels>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Medical DA (I)</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Medical DA (I)</v-expansion-panel-header>
              <v-expansion-panel-content>
                <div class='videoAndNotesContainer'>
                  <div class='videoContainer'>
                    <video id='medicalDAIVideo' width='640' height='400' controls='controls'>
                      <source src='https://www.dropbox.com/s/kcd3p8gomt1qxec/Intake%20Team%20Training%20Medica%20DA%20and%20DACA.mp4?raw=1' type='video/mp4'/>
                    </video>
                  </div>
                  <div class='notesContainer' v-if='controlVariables.navigationBarDialog == false'>
                    <v-textarea class='notesInput' height='400' color='#C5B47E' v-model='userInputs.medicalDAINotesInput' outlined no-resize>
                      <template slot='append'>
                        <v-icon @click='copyTimeStampToNotesInput("medicalDAIVideo", "medicalDAINotesInput")' class='notesInputIcon' size='15'>mdi-timer-plus-outline</v-icon>
                        <v-icon @click='copyToClipboard(userInputs.medicalDAINotesInput)' class='notesInputIcon notesInputMidIcon' size='15'>mdi-content-copy</v-icon>
                        <v-icon @click='saveNotesInput("medicalDAINotesInput")' class='notesInputIcon' size='15'>mdi-content-save-outline</v-icon>
                      </template>
                    </v-textarea>
                  </div>
                </div>
              </v-expansion-panel-content>
            </v-expansion-panel>  

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Medical DA (II)</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Medical DA (II)</v-expansion-panel-header>
              <v-expansion-panel-content>
                <div class='videoAndNotesContainer'>
                  <div class='videoContainer'>
                    <video id='medicalDAIIVideo' width='640' height='400' controls='controls'>
                      <source src='https://www.dropbox.com/s/kcd3p8gomt1qxec/Intake%20Team%20Training%20Medica%20DA%20and%20DACA.mp4?raw=1' type='video/mp4'/>
                    </video>
                  </div>
                  <div class='notesContainer' v-if='controlVariables.navigationBarDialog == false'>
                    <v-textarea class='notesInput' height='400' color='#C5B47E' v-model='userInputs.medicalDAIINotesInput' outlined no-resize>
                      <template slot='append'>
                        <v-icon @click='copyTimeStampToNotesInput("medicalDAIIVideo", "medicalDAIINotesInput")' class='notesInputIcon' size='15'>mdi-timer-plus-outline</v-icon>
                        <v-icon @click='copyToClipboard(userInputs.medicalDAIINotesInput)' class='notesInputIcon notesInputMidIcon' size='15'>mdi-content-copy</v-icon>
                        <v-icon @click='saveNotesInput("medicalDAIINotesInput")' class='notesInputIcon' size='15'>mdi-content-save-outline</v-icon>
                      </template>
                    </v-textarea>
                  </div>
                </div>
              </v-expansion-panel-content>
            </v-expansion-panel>  

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>PIP and cuban adjustment</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>PIP y ajuste cubano</v-expansion-panel-header>
              <v-expansion-panel-content>
                <div class='videoAndNotesContainer'>
                  <div class='videoContainer'>
                    <video id='PIPVideo' width='640' height='400' controls='controls'>
                      <source src='https://www.dropbox.com/home/Intake%20training?preview=Training+PIP+and+Cuban+adjustment+act+By+Madison+and+Rea-20230201_110324-Meeting+Recording.mp4?raw=1' type='video/mp4'/>
                    </video>
                  </div>
                  <div class='notesContainer' v-if='controlVariables.navigationBarDialog == false'>
                    <v-textarea class='notesInput' height='400' color='#C5B47E' v-model='userInputs.PIPNotesInput' outlined no-resize>
                      <template slot='append'>
                        <v-icon @click='copyTimeStampToNotesInput("PIPVideo", "PIPNotesInput")' class='notesInputIcon' size='15'>mdi-timer-plus-outline</v-icon>
                        <v-icon @click='copyToClipboard(userInputs.PIPNotesInput)' class='notesInputIcon notesInputMidIcon' size='15'>mdi-content-copy</v-icon>
                        <v-icon @click='saveNotesInput("PIPNotesInput")' class='notesInputIcon' size='15'>mdi-content-save-outline</v-icon>
                      </template>
                    </v-textarea>
                  </div>
                </div>
              </v-expansion-panel-content>
            </v-expansion-panel>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Asylum and juvenile VISA</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>VISA de asilo y de menores</v-expansion-panel-header>
              <v-expansion-panel-content>
                <div class='videoAndNotesContainer'>
                  <div class='videoContainer'>
                    <video id='juvenileVISAVIdeo' width='640' height='400' controls='controls'>
                      <source src='https://www.dropbox.com/s/6kl53nt2mvcibsb/Training%20asylum%20and%20Juvenile%20visa-20221117_090724-Meeting%20Recording%20%281%29.mp4?raw=1' type='video/mp4'/>
                    </video>
                  </div>
                  <div class='notesContainer' v-if='controlVariables.navigationBarDialog == false'>
                    <v-textarea class='notesInput' height='400' color='#C5B47E' v-model='userInputs.juvenileVISANotesInput' outlined no-resize>
                      <template slot='append'>
                        <v-icon @click='copyTimeStampToNotesInput("juvenileVISAVIdeo", "juvenileVISANotesInput")' class='notesInputIcon' size='15'>mdi-timer-plus-outline</v-icon>
                        <v-icon @click='copyToClipboard(userInputs.juvenileVISANotesInput)' class='notesInputIcon notesInputMidIcon' size='15'>mdi-content-copy</v-icon>
                        <v-icon @click='saveNotesInput("juvenileVISANotesInput")' class='notesInputIcon' size='15'>mdi-content-save-outline</v-icon>
                      </template>
                    </v-textarea>
                  </div>
                </div>
              </v-expansion-panel-content>
            </v-expansion-panel>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>General notes</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Apuntes generales</v-expansion-panel-header>
              <v-expansion-panel-content>
                <div class='videoAndNotesContainer'>
                  <div class='videoContainer'>
                    <video id='generalNotesVideo' width='640' height='400' controls='controls'>
                      <source src='https://www.dropbox.com/s/cdl8xctru4qkaqx/Training%20Intake%20Notes%20%20.mp4?raw=1' type='video/mp4'/>
                    </video>
                  </div>
                  <div class='notesContainer' v-if='controlVariables.navigationBarDialog == false'>
                    <v-textarea class='notesInput' height='400' color='#C5B47E' v-model='userInputs.generalNotesNotesInput' outlined no-resize>
                      <template slot='append'>
                        <v-icon @click='copyTimeStampToNotesInput("generalNotesVideo", "generalNotesNotesInput")' class='notesInputIcon' size='15'>mdi-timer-plus-outline</v-icon>
                        <v-icon @click='copyToClipboard(userInputs.generalNotesNotesInput)' class='notesInputIcon notesInputMidIcon' size='15'>mdi-content-copy</v-icon>
                        <v-icon @click='saveNotesInput("generalNotesNotesInput")' class='notesInputIcon' size='15'>mdi-content-save-outline</v-icon>
                      </template>
                    </v-textarea>
                  </div>
                </div>
              </v-expansion-panel-content>
            </v-expansion-panel>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel expansionPanelHeaderQuizLabel' v-if='controlVariables.currentLanguage == "ENG"' @click='openTest(5)'>Quiz (V): DACA, medical DA, PIP and asylum</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel expansionPanelHeaderQuizLabel' v-else @click='openTest(5)'>Quiz (V): DACA, medical DA, PIP y asilo</v-expansion-panel-header>
            </v-expansion-panel>

          </v-expansion-panels>
          
        </v-expansion-panel-content>
      </v-expansion-panel>

      <v-expansion-panel>
        <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Notes</v-expansion-panel-header>
        <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Apuntes</v-expansion-panel-header>
        <v-expansion-panel-content>
          
          <label class='expansionPanelContentLabel' v-if='controlVariables.currentLanguage == "ENG"'>Here you can consult all of Intake's Team notes in one place</label>
          <label class='expansionPanelContentLabel' v-else>Aquí podras consultar todos los apuntes del Intake Team en un solo lugar</label>
          <br><br>

          <v-expansion-panels>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Post consultation notes</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Notas posteriores a la consulta</v-expansion-panel-header>
              <v-expansion-panel-content>
                <iframe height='400' width='100%' frameborder='0' src='https://res.cloudinary.com/dfionqbqe/image/upload/v1681765556/intakePostConsultionNotes.pdf'></iframe>            
              </v-expansion-panel-content>
            </v-expansion-panel>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Filling fees prices chart</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Cuadro de precios de filling fees</v-expansion-panel-header>
              <v-expansion-panel-content>
                <iframe height='400' width='100%' frameborder='0' src='https://res.cloudinary.com/dfionqbqe/image/upload/v1681490661/intakePricesChart.pdf'></iframe>            
              </v-expansion-panel-content>
            </v-expansion-panel>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Updated prices</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Precios actualizados</v-expansion-panel-header>
              <v-expansion-panel-content>
                <iframe height='400' width='100%' frameborder='0' src='https://res.cloudinary.com/dfionqbqe/image/upload/v1681766033/intakeUpdatedPrices.pdf'></iframe>            
              </v-expansion-panel-content>
            </v-expansion-panel>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Cheat 3/10 years bar</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Evitar el bar de 3/10 años</v-expansion-panel-header>
              <v-expansion-panel-content>
                <iframe height='400' width='100%' frameborder='0' src='https://res.cloudinary.com/dfionqbqe/image/upload/v1681767088/intakeCheatBar.pdf'></iframe>            
              </v-expansion-panel-content>
            </v-expansion-panel>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Case type cheat</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Trucos en función del caso</v-expansion-panel-header>
              <v-expansion-panel-content>
                <iframe height='400' width='100%' frameborder='0' src='https://res.cloudinary.com/dfionqbqe/image/upload/v1681767272/intakeCaseTypeCheat.pdf'></iframe>            
              </v-expansion-panel-content>
            </v-expansion-panel>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Value based selling</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Ventas basadas en el valor</v-expansion-panel-header>
              <v-expansion-panel-content>
                <iframe height='400' width='100%' frameborder='0' src='https://res.cloudinary.com/dfionqbqe/image/upload/v1681767427/intakeValueBasedSelling.pdf'></iframe>            
              </v-expansion-panel-content>
            </v-expansion-panel>

            <v-expansion-panel>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-if='controlVariables.currentLanguage == "ENG"'>Cases times</v-expansion-panel-header>
              <v-expansion-panel-header class='expansionPanelHeaderLabel' v-else>Tiempo de los casos</v-expansion-panel-header>
              <v-expansion-panel-content>
                <iframe height='400' width='100%' frameborder='0' src='https://res.cloudinary.com/dfionqbqe/image/upload/v1681767572/intakeCasesTimes.pdf'></iframe>            
              </v-expansion-panel-content>
            </v-expansion-panel>

          </v-expansion-panels>
          
        </v-expansion-panel-content>
      </v-expansion-panel>

      <v-expansion-panel>
        <v-expansion-panel-header class='expansionPanelHeaderLabel expansionPanelHeaderQuizLabel' v-if='controlVariables.currentLanguage == "ENG"' @click='openTest(6)'>Quiz (VI): general recap</v-expansion-panel-header>
        <v-expansion-panel-header class='expansionPanelHeaderLabel expansionPanelHeaderQuizLabel' v-else @click='openTest(6)'>Quiz (VI): resumen general</v-expansion-panel-header>
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
  .expansionPanelHeaderQuizLabel {
    background-color: #C5B47E;
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
  .notesInputIcon{
    cursor: pointer;
  }
  .notesInputMidIcon{
    margin-left: 7px;
    margin-right: 7px;
  }
</style>
  
<script>

  export default {
    components: {
    },

    name: 'IntakeTeamComponent',

    data: () => 
    ({
      controlVariables: 
      {
        currentLanguage: '',
        coppiedToClipboardSnackbar: false,
        navigationBarDialog: true
      },

      userInputs:
      {
        overviewGovernmentAgenciesNotesInput: '',
        familyBasedPetitionsNotesInput: '',
        consularProcessingNotesInput: '',
        trainingWithAngelAttorneyINotesInput: '',
        trainingWithReaINotesInput: '',
        humanitarianOptionsNotesInput: '',
        additionalInformationNotesInput: '',
        ethicsTrainingNotesInput: '',
        consultTrainingINotesInput: '',
        VAWAINotesInput: '',
        TVISANotesInput: '',
        permBarINotesInput: '',
        permBarIINotesInput: '',
        permBarIIINotesInput: '',
        permBarIVNotesInput: '',
        hypotheticalsNotesInput: '',
        miscellaneousINotesInput: '',
        miscellaneousIINotesInput: '',
        permBarVNotesInput: '',
        waiversNotesInput: '',
        crimesNotesInput: '',
        NATZNotesInput: '',
        medicalDAINotesInput: '',
        medicalDAIINotesInput: '',
        PIPNotesInput: '',
        juvenileVISANotesInput: '',
        generalNotesNotesInput: '',
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
      },

      copyTimeStampToNotesInput(videoID, notesInput){
        var date = new Date(null);
        date.setSeconds(document.getElementById(videoID).currentTime);
        var timeStamp = date.toISOString().substr(11, 8);
        if ((this.userInputs[notesInput] != '') && (this.userInputs[notesInput].slice(-1) != '\n')){
          this.userInputs[notesInput] = this.userInputs[notesInput] + '\n[' + timeStamp + ']: ';
        }
        else {
          this.userInputs[notesInput] = this.userInputs[notesInput] + '[' + timeStamp + ']: ';
        }
      },

      openTest(testID){
        alert(testID)
      }
    },

    created(){
      this.controlVariables.currentLanguage = 'ENG';
    },

    mounted: function () { 
      this.$root.$on('switchLanguage', (newLanguage) => {
        this.controlVariables.currentLanguage = newLanguage;
      })
      this.$root.$on('navigationBarDialog', (navigationBarDialog) => {
        this.controlVariables.navigationBarDialog = navigationBarDialog;
      })
    }
  }
</script>