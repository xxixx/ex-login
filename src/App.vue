<template>
  <v-app id="inspire">
    <v-navigation-drawer v-model="drawer" app >
      <!--  -->
    </v-navigation-drawer>

    <v-app-bar app color="primary" >
      <v-app-bar-nav-icon @click="drawer = !drawer" ></v-app-bar-nav-icon>

      <v-toolbar-title class="d-flex flex-collum" >
        <div>
          <!-- <v-list-item router :to="{name :'Home'}" style="color:white">Application </v-list-item> -->
          
        </div>
       <div >
         
          <v-list-item router :to="{name :'Home'}" style="color:white">Home </v-list-item>
        </div>
        <div >
         
          <v-list-item router :to="{name :'Login'}" style="color:white">Login </v-list-item>
        </div>
          
        
        </v-toolbar-title>
      
    </v-app-bar>

    <v-main>
      <router-view>
      </router-view>      <!--  -->
    </v-main>
  </v-app>
</template>

<script>
  export default {
    data: () => ({ drawer: null }),
  }
</script>
<style >
.nav-item{
  color: white!important;
  background-color:white!important;
}
</style>