<template>
  <div>
    <ul v-for="mountain in mountains" :key="mountain.id">
      <NuxtLink :to="`${mountain.continent.toLowerCase()}/${mountain.slug}`">
        <li>
          <span>{{ mountain.title }}</span>
          <span>{{mountain.continent.toLowerCase()}}</span>
          <span>{{mountain.slug}}</span>
        </li>
      </NuxtLink>
    </ul>
  </div>
</template>
<script>
export default {
  async asyncData() {
    const mountains = await fetch(
      'https://api.nuxtjs.dev/mountains'
    ).then((res) => res.json())

    return { mountains }
  }
}
</script>
