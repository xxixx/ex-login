<template>
<div id="app">
<nav class="navbar navbar-expand-lg navbar-light bg-success">
  <div class="container-fluid">
    <a class="navbar-brand" href="#">Navbar</a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav me-auto mb-2 mb-lg-0">
        <li class="nav-item" router :to="{name :'Home'}">
          <a class="nav-link active" aria-current="page"   href= "Home">Home</a>
        </li>
        <li class="nav-item" router :to="{name :'Home'}">
          <a class="nav-link active" aria-current="page"   href= "Login">Login</a>
        </li>
        
      
      </ul>
      
    </div>
  </div>
</nav>
  <!-- === -->
  <v-app id="">
    <div>
     
        
     
     <div class="d-flex justify-content-end">
        <v-toolbar-items >
              
                <v-btn v-if="isLogon" flat>welcome One</v-btn>
                <v-btn v-if="isLogon" flat>Link Two</v-btn>
              </v-toolbar-items>
            </div>
      
    </div>
     <v-main>
      <router-view>
      </router-view>      <!--  -->
    </v-main>
  </v-app>
  
</div>
</template>

<script>
  export default {
    data: () => ({ drawer: null,
       }
    ),
  }
</script>
<style >
.nav-item{
  color: white!important;
  /* background-color:white!important; */
}
.nav-item a{
  color: white!important;
  /* background-color:white!important; */
}
</style>