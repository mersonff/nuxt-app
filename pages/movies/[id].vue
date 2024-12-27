<script setup>
  const route = useRoute()
  const { data } = await useFetch(`https://www.omdbapi.com/?apikey=8e3f600b&i=${route.params.id}`, {
    pick: ['Plot', 'Title', 'Error', 'Poster'],
    key: `/movies/${route.params.id}`,
    onResponse({ request, response}) {
      if(response._data.Error === 'Incorrect IMDb ID.') {
        showError({ statusCode: 404, message: 'Movie not found' })
      }
    }
  });
  console.log(data)
  useHead({
    title: data?.value.Title,
    meta: [
      { name: 'description', content: data?.value.Plot },
      { property: 'og:title', content: data?.value.Title },
      { property: 'og:image', content: data?.value.Poster},
      { property: "twitter:card", content: `summary_large_image`}
    ]
  })
</script>

<template>
  <div>
    <pre>
      {{ data }}
    </pre>  
  </div>
</template>