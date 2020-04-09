<template>
  <v-toolbar color="orange darken-4" dark fixed>
    <v-toolbar-title class="mr-4 font-weight-bold">VUE TO DO LIST</v-toolbar-title>
    <v-toolbar-items>
    </v-toolbar-items>
    <v-spacer></v-spacer>
    <v-toolbar-items class="hidden-sm-and-down">
      <v-btn flat to="/register" v-if="!isLoggedIn" class="font-weight-bold">
        <v-icon class="mr-2 font-weight-bold">account_box</v-icon>
        Register
      </v-btn>
      <v-btn flat to="/login" v-if="!isLoggedIn" class="font-weight-bold">
        <v-icon class="mr-2">fingerprint</v-icon>
        Login
      </v-btn>
      <v-btn flat v-if="isLoggedIn" @click="logout" class="font-weight-bold">
        <v-icon class="mr-2">exit_to_app</v-icon>
        Logout
      </v-btn>
    </v-toolbar-items>
  </v-toolbar>
</template>

<script>
import { mapGetters, mapActions } from 'vuex';

export default {
  computed: {
    ...mapGetters('authentication', [
      'isLoggedIn',
    ]),
  },
  methods: {
    ...mapActions('authentication', [
      'logout',
    ]),
  },
};
</script>

<style>

</style>
