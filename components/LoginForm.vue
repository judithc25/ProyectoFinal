<template>
  <v-form @submit.prevent="login">
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
      Login
    </v-btn>
  </v-form>
</template>

<script>
export default {
  data () {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    login () {
      // Implement login logic here
      this.$emit('login', { email: this.email, password: this.password })
    }
  }
}
</script>
