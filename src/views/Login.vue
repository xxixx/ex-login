<template>
 <v-container fill-height style="max-width:450px" >
     <v-layout align-center row wrap >
         <v-flex x12>
              <v-alert :value="isSuccess" type="success" class="mb-3"> 로그인 되었습니다.</v-alert>
              <v-alert :value="isError" type="error" class="mb-3"> 올바른 이메일을 입력하세요.</v-alert>
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
                <v-btn @click="login()" block color="teal">로그인</v-btn>
                </div>
    </v-card>
   
        
        
         </v-flex>
     </v-layout>
 </v-container>
</template>

<script>
export default {
    data(){
        return{
            email : null,
            password : null,
            alluser : [
                {id :1, name: 'hoza', email : '1@a.com', password : '11111111'},
                {id : 2, name :'hoza2', email : '1@a.com', password : '11111111'}
            ],
            isError : false,
            isSuccess : false
        }
    },
    methods:{
        login(){
            console.log(this.email, this.password);
            //전체 user에서 해당 이메일로 유저를 찾는다.
            let selectedUser = null;
            this.alluser.forEach(user =>{
                if (user.email === this.email) selectedUser = user
            })
            // ==============
            // if (selectedUser === null) alert("이메일을 입력하세요")
            // else{
            //     if(selectedUser.password !== this.password)
            //     alert("이메일과 패스워드를 확인하세요")
            //     else{
            //         alert("로그인 되었습니다.")
              // =================
              
        //삼항 연산자로 코딩
             selectedUser === null
            //  ? alert("이메일을 입력하세요")
             ? (this.isError = true , this.isSuccess = false)
              
             : selectedUser.password !== this.password
            //    ? alert("이메일과 패스워드를 확인하세요")
               ? (this.isError = true)
            //    : alert("로그인 되었습니다.")
                : (this.isError = false , this.isSuccess = true)
              

        //삼항 연산자로 코딩
           
           
        }

    }
}
</script>

<style>

</style>