<template>
    <div class='languageIconContainer' @click='switchLanguage()'>
      <v-icon class='languageIcon' color='black'>mdi-earth</v-icon>
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
        currentLanguage: ''
      }),
  
      created(){
        this.currentLanguage = 'ENG';
      },
  
      methods: {
        switchLanguage(){
          if (this.currentLanguage == 'ENG'){
            this.currentLanguage = 'SPN';
          } else {
            this.currentLanguage = 'ENG';
          }
          this.$root.$emit('switchLanguage', this.currentLanguage);
        }
      }
    }
  </script>