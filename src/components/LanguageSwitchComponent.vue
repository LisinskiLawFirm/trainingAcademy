<template>
  <div class='languageIconContainer' @click='switchLanguage()'>
    <v-tooltip v-if='controlVariables.quizComponent == true' left>
      <template v-slot:activator="{ on, attrs }">
        <v-icon class='languageIcon' color='black' v-bind='attrs' v-on='on'>mdi-earth</v-icon>
      </template>
      <span v-if='controlVariables.currentLanguage == "ENG"'>Attention! When you change language, your answers will not be saved. You must submit your answers in english</span>
      <span v-else>¡Atención! Al cambiar de lenguaje, tus respuestas no se guardarán. Debes enviar tus respuestas en inglés</span>
    </v-tooltip>
    <v-icon class='languageIcon' color='black' v-else>mdi-earth</v-icon>
  </div>
</template>
    
<style scoped> 
.languageIconContainer{
  position: fixed;
  z-index: 1000;
  top: 90%;
  left: 95%;
  width: 45px;
  height: 45px;
  border-radius: 25px;
  text-align: center;
  background-color: #C5B47E;
  cursor: pointer;
}
.languageIcon{
  position: relative;
  top: 9px;
  cursor: pointer;
}
</style>
  
<script>
export default {
  name: 'LanguageSwitchComponent',

  data: () => 
  ({
    controlVariables: 
    {
      currentLanguage: '',
      quizComponent: false
    }
  }),

  created(){
    this.controlVariables.currentLanguage = 'ENG';
  },

  methods: {
    switchLanguage(){
      if (this.controlVariables.currentLanguage == 'ENG'){
        this.controlVariables.currentLanguage = 'SPN';
      } else {
        this.controlVariables.currentLanguage = 'ENG';
      }
      this.$root.$emit('switchLanguage', this.controlVariables.currentLanguage);
    }
  },

  mounted: function () { 
    this.$root.$on('openQuizComponent', () => {
      this.controlVariables.quizComponent = true;
    });

    this.$root.$on('closeQuizComponent', () => {
      this.controlVariables.quizComponent = false;
    });
  }
}
</script>