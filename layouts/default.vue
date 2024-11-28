<template>
  <v-app dark>
    <v-navigation-drawer
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
      <v-btn icon>
        <v-icon>mdi-account-injury</v-icon>
      </v-btn>
      <span>Prasad</span>
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
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
      title: 'Medicorazon'
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
