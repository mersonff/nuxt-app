<script setup>
useHead({
  titleTemplate: (titleChunk) => titleChunk ? `${titleChunk} - Nuxt Movie App` : 'Nuxt Movie App',
})
</script>
<template>
  <div>
    <NuxtLayout>
      <NuxtPage />
    </NuxtLayout> 
  </div>
</template>
