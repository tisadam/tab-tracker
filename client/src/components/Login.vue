<template>
  <v-layout column>
    <v-flex xs6 offset-xs3>
      <div class="white elevation-2">
        <v-toolbar flat dense class="cyan" dark>
          <v-toolbar-title>Login</v-toolbar-title>
        </v-toolbar>

        <div class="pl-4 pr-4 pt-2 pb-2">
          <v-text-field
          label="Email"
          v-model="Email"
          ></v-text-field>

          <br>
          <v-text-field
          label="Password"
          v-model="Password"
          ></v-text-field>

            <br>
            <div class="error" v-html="error" />
            <br>
            <v-btn
              class="cyan"
              @click="login">
              login</v-btn>
        </div>

      </div>
    </v-flex>
  </v-layout>

</template>

<script>
import AuthenticationService from '@/services/AuthenticationService'
export default {
  data () {
    return {
      email: '',
      password: '',
      error: null
    }
  },
  methods: {
    async login () {
      try {
        await AuthenticationService.Login({
          email: this.email,
          password: this.password
        })
        // console.log(response.data)
      } catch (error) {
        this.error = error.response.data.error
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.error {
  color: red;
}

.toolbar__title {
  color: white;
}
</style>
