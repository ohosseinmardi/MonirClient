<template>
  <div class="app flex-row align-items-center">
    <div class="container">
      <b-row class="justify-content-center">
        <b-col md="6" sm="8">
          <b-card no-body class="mx-4">
            <b-card-body class="p-4">
              <h1>Register</h1>
              <p class="text-muted">Create your account</p>
              <!--<b-input-group class="mb-3">-->
                <!--<b-input-group-prepend>-->
                  <!--<b-input-group-text><i class="icon-user"></i></b-input-group-text>-->
                <!--</b-input-group-prepend>-->
                <!--<input type="text" class="form-control" placeholder="Username">-->
              <!--</b-input-group>-->

              <b-input-group class="mb-3">
                <b-input-group-prepend>
                  <b-input-group-text>@</b-input-group-text>
                </b-input-group-prepend>
                <input type="text" class="form-control" placeholder="Email" v-model="email">
              </b-input-group>

              <b-input-group class="mb-3">
                <b-input-group-prepend>
                  <b-input-group-text><i class="icon-lock"></i></b-input-group-text>
                </b-input-group-prepend>
                <input type="password" class="form-control" placeholder="Password" v-model="password">
              </b-input-group>

              <b-input-group class="mb-4">
                <b-input-group-prepend >
                  <b-input-group-text ><i class="icon-lock"></i></b-input-group-text>
                </b-input-group-prepend>
                <input type="password" class="form-control" placeholder="Repeat password" v-model="rep_password">
              </b-input-group>

              <b-button v-on:click="register" variant="success" block>Create Account</b-button>
              <b-button v-on:click="login" style="color: green"variant="link" class="px-0">Already have an account? Sign in!</b-button>

            </b-card-body>
            <!--<b-card-footer class="p-4">-->
              <!--<b-row>-->
                <!--<b-col cols="6">-->
                  <!--<b-button block class="btn btn-facebook"><span>facebook</span></b-button>-->
                <!--</b-col>-->
                <!--<b-col cols="6">-->
                  <!--<b-button block class="btn btn-twitter" type="button"><span>twitter</span></b-button>-->
                <!--</b-col>-->
              <!--</b-row>-->
            <!--</b-card-footer>-->
          </b-card>
        </b-col>
      </b-row>
    </div>
  </div>
</template>

<script>
  import firebaseInit from './firebaseInit';
  import firebase from 'firebase';

export default {
  name: 'Register',
  data: function () {
    return {
      email: '',
      password: '',
      rep_password: ''
    };
  },
  methods: {
    register: function (e) {
      if (this.password === this.rep_password) {
        firebase
          .auth()
          .createUserWithEmailAndPassword(this.email, this.password)
          .then(
            user => {
              // console.log(user);
              window.alert(user.user.email);
//            alert(`Account Created for ${user}`);
              this.$router.push('/')
            },
            err => {
              alert(err.message);
            }
          );
        e.preventDefault();
      }
      else {
        window.alert("Passwords dont match");
      }
    },
    login: function(e){
      this.$router.push('./login')
    }
  }
}
</script>
