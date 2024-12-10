<template>
  <v-form @submit.prevent="signup">
    <v-text-field
      v-model="name"
      label="Name"
      required
    />
    <v-text-field
      v-model="email"
      label="Email"
      required
    />
    <v-text-field
      v-model="password"
      label="Password"
      type="password"
      required
    />
    <v-btn type="submit" color="primary">
      Sign Up
    </v-btn>
  </v-form>
</template>

<script>
export default {
  data () {
    return {
      name: '',
      email: '',
      password: ''
    }
  },
  methods: {
    signup () {
      // Implement signup logic here
      this.$emit('signup', { name: this.name, email: this.email, password: this.password })
    }
  }
}
</script>
