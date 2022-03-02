<script setup>
import { useAuth0, AuthState } from "./utils/useAuth0";
import ToDo from "./components/ToDo.vue";
const { login, logout, initAuth } = useAuth0(AuthState);

initAuth();
</script>

<template>
  <div v-if="!AuthState.loading">
    <div v-if="!AuthState.isAuthenticated">
      Please Click Here to login:
      <button @click="login()" class="btn btn-primary">Login</button>
    </div>

    <div v-else>
      <p>
        Welcome to VueAuth <strong>{{ AuthState.user.name }}</strong>
      </p>
      <button @click="logout()" class="btn btn-secondary">Logout</button>
      <ToDo> </ToDo>
    </div>
  </div>

  <div v-else>Loading ...</div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
