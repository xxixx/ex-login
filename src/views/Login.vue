<template>
 <v-container fill-height style="max-width:450px" >
     <v-layout align-center row wrap >
         <v-flex x12>
               <div v-if="isLogin" class="alert alert-success" role="alert" style="background: var(--bs-success);color: var(--bs-white);"><span><strong>Alert</strong> 로그인 되었습니다.</span></div>
            <div v-if="loginError" class="alert alert-success" role="alert" style="background: var(--bs-orange);color: var(--bs-white);"><span><strong>Alert</strong> 이메일을 입력하세요.</span></div>
              <v-alert  v-if="isLogin" type="success" class="mb-3"> 로그인 되었습니다.</v-alert>
              <v-alert  v-if="loginError" type="error" class="mb-3"> 올바른 이메일을 입력하세요.</v-alert>
     <v-card>
        <v-toolbar flat dense color="teal">
            <v-toolbar-title>Login</v-toolbar-title>
            <v-spacer></v-spacer>
        </v-toolbar>
                <div class="pa-3">
                <v-col  cols="12"   sm="12"  md="12">
                <v-text-field v-model="email" label="email" ></v-text-field>
                </v-col>
                <v-col    cols="12" sm="12" md="12"><v-text-field v-model="password" label="password"></v-text-field>
                </v-col>
                <v-btn  @click="login({email:email, password:password})" block color="teal">로그인</v-btn>
                </div>
    </v-card>
   
        
        
         </v-flex>
     </v-layout>
 </v-container>
</template>

<script>
import {mapState ,mapActions} from "vuex"
export default {
    data(){
        return{
            email : null,
            password : null,
            // alluser : [
            //     {id :1, name: 'hoza', email : '1@a.com', password : '11111111'},
            //     {id : 2, name :'hoza2', email : '1@a.com', password : '11111111'}
            // ],
            // isError : false,
            // isSuccess : false
        }
    },
    computed: {
            ...mapState(['isLogin', 'loginError'])
    },
    
    methods:{
        ...mapActions(['login'])
        // login(){
        //     console.log(this.email, this.password);
        //     let selectedUser = null;
        //     this.alluser.forEach(user =>{
        //         if (user.email === this.email) selectedUser = user
        //     })
          
        //      selectedUser === null
        //      ? (this.isError = true , this.isSuccess = false)
              
        //      : selectedUser.password !== this.password
        //        ? (this.isError = true)
        //         : (this.isError = false , this.isSuccess = true)
        // }
    }
}
</script>

<style>

</style>