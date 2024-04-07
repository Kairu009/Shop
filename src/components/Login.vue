<template>
  <div>
    <h2>Login</h2>
    <form @submit.prevent="login">
      <div>
        <label for="username">Username:</label>
        <input type="text" id="username" v-model="username">
      </div>
      <div>
        <label for="password">Password:</label>
        <input type="password" id="password" v-model="password">
      </div>
      <button type="submit">Login</button>
      <div v-if="error" class="error">{{ error }}</div>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      username: '',
      password: '',
      error: ''
    };
  },
  methods: {
    login() {
      // Simulate authentication by checking username and password (dummy authentication)
      if (this.username === 'user' && this.password === 'password') {
        // Generate a token (dummy token for demonstration)
        const token = 'dummy_token';
        // Store the token in local storage
        localStorage.setItem('token', token);
        // Redirect to the home page after successful login
        this.$router.push('/home');
      } else {
        this.error = 'Invalid username or password';
      }
    }
  }
};
</script>

<style scoped>
.error {
  color: red;
}
</style>
