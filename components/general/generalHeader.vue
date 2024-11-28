<template>
  <v-app-bar app color="primary" dark>
    <v-app-bar-nav-icon class="d-sm-none" @click.stop="drawer = !drawer" />

    <v-toolbar-title class="d-flex align-center">
      <v-img
        src="/path/to/your/logo.png"
        max-height="40"
        max-width="40"
        contain
        class="mr-3"
      />
      <span>Your Hospital Name</span>
    </v-toolbar-title>

    <v-spacer />

    <v-toolbar-items class="hidden-xs-only">
      <v-btn text to="/" exact>
        Home
      </v-btn>
      <v-btn text to="/appointment">
        Appointment
      </v-btn>
      <v-btn text to="/services">
        Services
      </v-btn>
      <v-btn text to="/about">
        About Us
      </v-btn>
      <v-btn text to="/contact">
        Contact Us
      </v-btn>
    </v-toolbar-items>

    <v-spacer />

    <v-btn text to="/login">
      Sign In
    </v-btn>
    <v-btn outlined to="/register">
      Register
    </v-btn>

    <v-navigation-drawer
      v-model="drawer"
      absolute
      temporary
      right
    >
      <v-list nav dense>
        <v-list-item-group>
          <v-list-item to="/" exact>
            <v-list-item-title>Home</v-list-item-title>
          </v-list-item>
          <v-list-item to="/appointment">
            <v-list-item-title>Appointment</v-list-item-title>
          </v-list-item>
          <v-list-item to="/services">
            <v-list-item-title>Services</v-list-item-title>
          </v-list-item>
          <v-list-item to="/about">
            <v-list-item-title>About Us</v-list-item-title>
          </v-list-item>
          <v-list-item to="/contact">
            <v-list-item-title>Contact Us</v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
  </v-app-bar>
</template>

<script>
export default {
  name: 'GeneralHeaderLogin',
  data () {
    return {
      drawer: false
    }
  }
}
</script>

<style scoped>
/* Add any component-specific styles here */
</style>
