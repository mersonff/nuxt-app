<script setup>
const user = useUser()
definePageMeta({
  layout: 'plain',
});
</script>
<template>
  <div>
    <h1>Login</h1>
    <form @submit.prevent="user.login">
      <input type="text" v-model="email" placeholder="Email" />
      <input type="password" v-model="password" placeholder="Password" />
      <button type="submit">Login</button>
    </form>
  </div>
</template>