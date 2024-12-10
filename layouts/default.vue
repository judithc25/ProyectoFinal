<template>
  <v-app dark>
    <v-navigation-drawer
      v-if="isAuthenticated"
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
      permanent
      class="panel"
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar
      v-if="isAuthenticated"
      :clipped-left="clipped"
      fixed
      app
      color="white"
      flat
    >
      <v-app-bar-nav-icon class="bar" @click.stop="drawer = !drawer" />
      <v-btn
        icon
        @click.stop="miniVariant = !miniVariant"
      >
        <v-icon>mdi-{{ `chevron-${miniVariant ? 'right' : 'left'}` }}</v-icon>
      </v-btn>
      <v-toolbar-title class="title" v-text="title" />
      <v-spacer />
      <v-btn icon @click="logout">
        <v-icon>mdi-logout</v-icon>
      </v-btn>
      <span>{{ userName }}</span>
    </v-app-bar>
    <v-main>
      <v-container>
        <template v-if="isAuthenticated">
          <Nuxt />
        </template>
        <template v-else>
          <v-tabs v-model="tab">
            <v-tab>Login</v-tab>
            <v-tab>Sign Up</v-tab>
          </v-tabs>
          <v-tabs-items v-model="tab">
            <v-tab-item>
              <LoginForm @login="handleLogin" />
            </v-tab-item>
            <v-tab-item>
              <SignupForm @signup="handleSignup" />
            </v-tab-item>
          </v-tabs-items>
        </template>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import LoginForm from '~/components/LoginForm.vue'
import SignupForm from '~/components/SignupForm.vue'

export default {
  name: 'DefaultLayout',
  components: {
    LoginForm,
    SignupForm
  },
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-gauge',
          title: 'Dashboard',
          to: '/'
        },
        {
          icon: 'mdi-heart-pulse',
          title: 'Medicine',
          to: '/inspire'
        },
        {
          icon: 'mdi-account-multiple',
          title: 'Staff',
          to: '/staff'
        },
        {
          icon: 'mdi-medication',
          title: 'Lab',
          to: '/lab'
        },
        {
          icon: 'mdi-home',
          title: 'Ward',
          to: '/ward'
        },
        {
          icon: 'mdi-needle',
          title: 'Treatment',
          to: '/treatment'
        },
        {
          icon: 'mdi-hospital-building',
          title: 'Pharmary',
          to: '/pharmary'
        },
        {
          icon: 'mdi-account-injury',
          title: 'Patient',
          to: '/patient'
        },
        {
          icon: 'mdi-ambulance',
          title: 'Supplier',
          to: '/supplier'
        },
        {
          icon: 'mdi-medical-cotton-swab',
          title: 'Prescription',
          to: '/prescription'
        },
        {
          icon: 'mdi-clipboard-pulse',
          title: 'Appoiment',
          to: '/appoiment'
        },
        {
          icon: 'mdi-account-heart',
          title: 'Depatment',
          to: '/depatment'
        },
        {
          icon: 'mdi-radiology-box',
          title: 'inovoice',
          to: '/inovoice'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Medicorazon',
      isAuthenticated: false,
      userName: '',
      tab: null
    }
  },
  methods: {
    handleLogin (credentials) {
      // Implement your login logic here
      // For demonstration, we'll just set isAuthenticated to true
      this.isAuthenticated = true
      this.userName = credentials.email
    },
    handleSignup (userData) {
      // Implement your signup logic here
      // For demonstration, we'll just set isAuthenticated to true
      this.isAuthenticated = true
      this.userName = userData.name
    },
    logout () {
      this.isAuthenticated = false
      this.userName = ''
    }
  }
}
</script>

<style scoped>
.panel {
  background: linear-gradient(-90deg,#8377a0, #8e81cc);
}
.title {
  margin-left: 38%
}
.bar {
  background: linear-gradient(-90deg,#8377a0, #8e81cc);
}
.tabla {
  margin-left: 20%;
}
.contenedor{
  margin-left: 20%;
  margin-right: 50%;
  margin-top: 10%;
}
</style>
