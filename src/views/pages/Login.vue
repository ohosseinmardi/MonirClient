<template>
  <div class="app flex-row align-items-center">
    <div class="container">
      <b-row class="justify-content-center">
        <b-col md="5">
          <b-card-group>
            <b-card no-body class="p-4">
              <b-card-body>
                <h1>Login</h1>
                <p class="text-muted">Sign In to your account</p>
                <b-input-group class="mb-3">
                  <b-input-group-prepend><b-input-group-text><i class="icon-user"></i></b-input-group-text></b-input-group-prepend>
                  <input type="text" class="form-control" placeholder="Email" v-model="email">
                </b-input-group>
                <b-input-group class="mb-4">
                  <b-input-group-prepend><b-input-group-text><i class="icon-lock"></i></b-input-group-text></b-input-group-prepend>
                  <input type="password" class="form-control" placeholder="Password" v-model="password">
                </b-input-group>
                <b-row>
                  <b-col cols="6">
                    <b-button v-on:click="login" variant="primary" class="px-4">Login</b-button>
                  </b-col>
                  <b-col cols="6" class="text-right">
                    <b-button variant="link" class="px-0">Forgot password?</b-button>
                  </b-col>
                </b-row>
              </b-card-body>
            </b-card>
            <!--<b-card no-body class="text-white bg-primary py-5 d-md-down-none" style="width:44%">-->
              <!--<b-card-body class="text-center">-->
                <!--<div>-->
                  <!--<h2>Sign up</h2>-->
                  <!--<b-button v-on:click="register" variant="primary" class="active mt-3">Register Now!</b-button>-->
                <!--</div>-->
              <!--</b-card-body>-->
            <!--</b-card>-->
          </b-card-group>
        </b-col>
      </b-row>
    </div>
  </div>
</template>



<script>
  import firebase from 'firebase';

  export default {
    name: 'Login',
    data: function() {
      return {
        email: '',
        password: ''
      };
    },
    methods: {
      login: function(e) {
        firebase
          .auth()
          .signInWithEmailAndPassword(this.email, this.password)
          .then(
            user => {
              // console.log(user);
              this.$router.push('/')
            },
            err => {
              alert(err.message);
            }
          );
        e.preventDefault();
      },
      register: function(){
        this.$router.push('./register')
      }
    }
  }
</script>
