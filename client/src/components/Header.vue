<template>
<v-toolbar fixed class="blue-grey lighten-4">
  <v-toolbar-title class="mr-4">
<span class="home">
    <router-link to="HelloWorld">
    HeaderTitle
    </router-link>
  </span>
  </v-toolbar-title>

    <v-toolbar-items>
      <v-btn flat dark>
        Browse
      </v-btn>
      </v-toolbar-items>
      <v-spacer></v-spacer>
        <v-toolbar-items>
          <router-link to="register">
          <v-btn flat dark>
            Sign up
          </v-btn>
          </router-link>
        </v-toolbar-items>
</v-toolbar>
</template>

<script>
export default {

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.home {
  cursor: pointer;
}

.home:hover {
  color: #E9E;
}
</style>
