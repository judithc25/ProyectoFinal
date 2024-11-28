<template>
  <v-footer
    padless
    class="mt-4"
  >
    <v-container>
      <v-row>
        <!-- Logo Section -->
        <v-col cols="12" sm="3" class="text-center text-sm-left">
          <v-img
            src="/path/to/your/logo.png"
            max-height="80"
            max-width="80"
            contain
            class="mx-auto mx-sm-0 mb-4"
          />
        </v-col>

        <!-- Quick Links Section -->
        <v-col cols="12" sm="3">
          <h3 class="text-h6 mb-3">
            Quick Links
          </h3>
          <v-list dense>
            <v-list-item v-for="(link, index) in quickLinks" :key="index" :to="link.to" link>
              <v-list-item-content>
                <v-list-item-title>{{ link.text }}</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-list>
        </v-col>

        <!-- Hours Section -->
        <v-col cols="12" sm="3">
          <h3 class="text-h6 mb-3">
            Hours
          </h3>
          <v-list dense>
            <v-list-item v-for="(day, index) in hours" :key="index">
              <v-list-item-content>
                <v-list-item-title>{{ day.day }}: {{ day.hours }}</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-list>
        </v-col>

        <!-- Contact Section -->
        <v-col cols="12" sm="3">
          <h3 class="text-h6 mb-3">
            Contact
          </h3>
          <v-list dense>
            <v-list-item>
              <v-list-item-content>
                <v-list-item-title>Phone: {{ phoneNumber }}</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
            <v-list-item>
              <v-list-item-content>
                <v-list-item-title>Email: {{ email }}</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
            <v-list-item :href="facebookUrl" target="_blank" link>
              <v-list-item-content>
                <v-list-item-title>
                  <v-icon left>
                    mdi-facebook
                  </v-icon>
                  Facebook
                </v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-list>
        </v-col>
      </v-row>
    </v-container>
  </v-footer>
</template>

<script>
export default {
  name: 'GeneralFooterTemplate',
  data () {
    return {
      quickLinks: [
        { text: 'Home', to: '/' },
        { text: 'Appointment', to: '/appointment' },
        { text: 'Services', to: '/services' },
        { text: 'About Us', to: '/about' },
        { text: 'Contact Us', to: '/contact' }
      ],
      hours: [
        { day: 'Monday', hours: '9:00 - 18:00' },
        { day: 'Tuesday', hours: '9:00 - 18:00' },
        { day: 'Wednesday', hours: '9:00 - 18:00' },
        { day: 'Thursday', hours: '9:00 - 18:00' },
        { day: 'Friday', hours: '9:00 - 18:00' }
      ],
      phoneNumber: '+1 234 567 8900',
      email: 'info@yourhospital.com',
      facebookUrl: 'https://www.facebook.com/yourhospital'
    }
  }
}
</script>

<style scoped>
/* Add any component-specific styles here */
</style>
