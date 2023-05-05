<template>
  <v-dialog width='800' v-model='controlVariables.quizDialog' persistent>

    <v-card>

      <v-card-title class='text-h5 grey lighten-2'>
        {{displayedPageContent.title}}
      </v-card-title>

      <v-card-text>
        <br>
        <template v-for='quizItem in displayedPageContent.quizItems'>
          <div class='quizItemContainer' :key='quizItem' v-if='quizItem.type == "Single selection"'>
            <h3>{{quizItem.title}}</h3>
            <v-radio-group v-model='quizItem.selectedOption'>
              <v-radio color='#C5B47E' v-for='option in quizItem.options' :key='option' :label='option.title' :value='option.title'></v-radio>
            </v-radio-group>
          </div>
          <div class='quizItemContainer' :key='quizItem' v-if='quizItem.type == "Multiple selection"'>
            <h3>{{quizItem.title}}</h3>
            <br>
            <v-checkbox color='#C5B47E' v-model='quizItem.selectedOption' v-for='option in quizItem.options' :key='option' :label='option.title' :value='option.title' dense></v-checkbox>
          </div>
          <div class='quizItemContainer' :key='quizItem' v-if='quizItem.type == "Writing"'>
            <h3>{{quizItem.title}}</h3>
            <br>
            <v-textarea class='quizWritingItemInput' color='#C5B47E' v-model='quizItem.selectedOption' outlined></v-textarea>
          </div>
          <br :key='quizItem'>
        </template>
      </v-card-text>

      <v-divider></v-divider>

      <v-card-actions>
        <v-spacer></v-spacer>
        <div class='quizButtonsContainer'>
          <v-btn class='quizCancelButton' color='gray' v-if='controlVariables.currentLanguage == "ENG"' @click='closeQuiz()'>Close quiz</v-btn>
          <v-btn class='quizCancelButton' color='gray' v-else @click='closeQuiz()'>Cerrar quiz</v-btn>
          <v-btn color='#C5B47E' v-if='controlVariables.currentLanguage == "ENG"' @click='endQuiz()'>End quiz</v-btn>
          <v-btn color='#C5B47E' v-else @click='endQuiz()'>Finalizar quiz</v-btn>
        </div>
      </v-card-actions>

    </v-card>
  </v-dialog>

</template>
  
<style scoped>
  .quizItemContainer{
    border-style: solid;
    border-width: 1px;
    border-radius: 5px;
    padding: 10px;
    border-color: gray;
  }
  .quizWritingItemInput{
    margin-left: 10px;
    margin-right: 10px;
  }

  .quizButtonsContainer{
    margin-top: 5px;
    margin-bottom: 5px;
  }

  .quizCancelButton{
    margin-right: 15px;
  }
</style>

<script>
export default {
  name: 'QuizComponent',
  components: {},

  data: () => ({
    controlVariables: 
    {
      currentLanguage: '',
      quizDialog: false
    },
    pageContentEnglish: {},
    pageContentSpanish: {},
    displayedPageContent: {}
  }),

  methods: {
    endQuiz(){
      let quizItemNotAnswered = true;
      for (let quizItemIndex in this.displayedPageContent.quizItems){
        console.log()
      }

      this.controlVariables.quizDialog = false;
      this.$root.$emit('closeQuizComponent');
    },

    closeQuiz(){
      this.controlVariables.quizDialog = false;
      this.$root.$emit('closeQuizComponent');
    }
  },

  created(){
  },

  mounted: function () { 
      this.$root.$on('openQuizComponent', (quizComponentContent, currentLanguage) => {
        this.controlVariables.currentLanguage = currentLanguage;
        this.controlVariables.quizDialog = true;
        this.pageContentEnglish = quizComponentContent.pageContentEnglish;
        this.pageContentSpanish = quizComponentContent.pageContentSpanish;
        if (currentLanguage == 'ENG'){
          this.displayedPageContent = this.pageContentEnglish;
        } else {
          this.displayedPageContent = this.pageContentSpanish;
        }

      });

      this.$root.$on('switchLanguage', (newLanguage) => {
        this.controlVariables.currentLanguage = newLanguage;
        if (newLanguage == 'ENG') {
          this.displayedPageContent = this.pageContentEnglish;
        } else {
          this.displayedPageContent = this.pageContentSpanish;
        }
      })
  }
}
</script>
  