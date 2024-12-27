<script setup>
const user = useUser()
const isLoggedIn = user.isLoggedIn
</script>
<template>
  <div>
    <nav style="display: flex; gap: 10px;">
      <NuxtLink to="/">Home</NuxtLink> |
      <NuxtLink to="/movies">Movies</NuxtLink>
      <NuxtLink v-if="!isLoggedIn" to="/login">Login</NuxtLink>
      <a href="#" v-else @click="isLoggedIn = false">Logout</a>
    </nav>
    <slot></slot>
  </div>
</template>