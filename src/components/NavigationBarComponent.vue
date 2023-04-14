<template>
  <div>
    <v-app-bar color='#C5B47E' app dark>
      <v-app-bar-nav-icon @click='openCloseNavigationBarDialog()'></v-app-bar-nav-icon>
      <v-app-bar-title>
        <strong>
          {{displayedPageContent.navigationBarTitle}}
        </strong>
      </v-app-bar-title>
    </v-app-bar>
    
    <v-navigation-drawer v-model='controlVariables.navigationBarDialog' width='300' app>
      <v-list-item>
        <v-list-item-content>
          <div class='userInformationContainer'>
            <div class='userProfilePictureContainer'>
              <v-avatar class='userProfilePicture'>
                <v-img :src='backendContent.profilePicture'></v-img>
              </v-avatar>
            </div>
            <div class='userNameEmailContainer'>
              <v-list-item-title class='text-h6'>{{backendContent.userName}}</v-list-item-title>
              <v-list-item-subtitle>{{backendContent.userEmail}}</v-list-item-subtitle>
            </div>
          </div>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense>
        <v-list-item v-for='navigationBarCategory in displayedPageContent.navigationBarCategories' :key='navigationBarCategory.title' @click='openNavigationBarCategory(navigationBarCategory.title)'>
          <v-list-item-icon>
            <v-icon>{{navigationBarCategory.icon}}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>{{navigationBarCategory.title}}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>

      <div class='navigationBarBottomOptionsContainer'>
        <v-list dense>
          <v-list-item v-for='navigationBarOption in displayedPageContent.navigationBarOptions' :key='navigationBarOption.title' @click='openNavigationBarOption(navigationBarOption.title)'>
            <v-list-item-icon>
              <v-icon>{{navigationBarOption.icon}}</v-icon>
            </v-list-item-icon>
            <v-list-item-content>
              <v-list-item-title>{{navigationBarOption.title}}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list>
      </div>
    </v-navigation-drawer>
  </div>
</template>

<style scoped> 
  .userInformationContainer{
    display: flex;
  }
  .userProfilePictureContainer{
    margin-right: 15px;
  }
  .userProfilePicture{
    max-width: 20px;
  }
  .userNameEmailContainer{
    top: 3px; 
    position: relative;
  }
  .navigationBarBottomOptionsContainer{
    position: absolute; 
    bottom: 0px; 
    width: 300px;
  }

</style>

<script>
  export default {
    name: 'NavigationBarComponent',

    data: () => 
    ({
      controlVariables:
      {
        navigationBarDialog: false,
      },

      backendContent:
      {
        profilePicture: 'https://cdn.vuetifyjs.com/images/john.jpg',
        userName: 'Oscar Araya',
        userEmail: 'oaraya@lisinskifirm.com',
      },

      pageContentSpanish: 
      {
        navigationBarTitle: 'Academia de Entrenamiento LLF',
        navigationBarCategories: [{title: 'Phone Operator', icon: 'mdi-phone'}, {title: 'Intake', icon: 'mdi-sale'}, {title: 'Sign-Up', icon: 'mdi-content-save'}, {title: 'Cliente Service Cordinator (CSC)', icon: 'mdi-progress-check'}],
        navigationBarOptions: [{title: 'Perfil', icon: 'mdi-account'}, {title: 'Cerrar sesión', icon: 'mdi-logout'}]
      },

      pageContentEnglish:
      {
        navigationBarTitle: 'LLF Training Academy',
        navigationBarCategories: [{title: 'Phone Operator', icon: 'mdi-phone'}, {title: 'Intake', icon: 'mdi-sale'}, {title: 'Sign-Up', icon: 'mdi-content-save'}, {title: 'Cliente Service Cordinator (CSC)', icon: 'mdi-progress-check'}],
        navigationBarOptions: [{title: 'Profile', icon: 'mdi-account'}, {title: 'Log Out', icon: 'mdi-logout'}]
      },

      displayedPageContent: {}
    }),

    methods: {
      openCloseNavigationBarDialog(){
        this.controlVariables.navigationBarDialog = !this.controlVariables.navigationBarDialog;
      },

      openNavigationBarCategory(navigationBarCategory){
        this.$root.$emit('openNavigationBarCategory', navigationBarCategory);
      },

      openNavigationBarOption(navigationBarOption){
        console.log(navigationBarOption);
      }
    },

    created(){
      this.displayedPageContent = this.pageContentEnglish;
    },

    mounted: function () { 
      this.$root.$on('switchLanguage', (newLanguage) => {
        if (newLanguage == 'ENG') {
          this.displayedPageContent = this.pageContentEnglish;
        } else {
          this.displayedPageContent = this.pageContentSpanish;
        }
      })
    }
    
  }
</script>