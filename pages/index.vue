<template>
  <div class="container">
    <div v-for="(filteredArticles, categoryKey) in groupedCategories" :key="categoryKey">
      <h2>{{ categoryKey }}</h2>
      <list-item v-for="article in filteredArticles" :key="article.slug">
        <template #title>
          {{ article.title }}
        </template>
        <template #content>
          <div> {{ article.description }}</div>
        </template>
        <br>
      </list-item>
      <hr>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData ({ $content }) {
    const articles = await $content('', { deep: true })
      .only(['title', 'description', 'img', 'slug', 'cat', 'dir'])
      .sortBy('createdAt', 'asc')
      .fetch()

    return { articles }
  },
  computed: {
    groupedCategories () {
      return this.articles.reduce((finalObject, obj) => {
        const directory = obj.dir
        finalObject[directory] ?? (finalObject[directory] = [])
        finalObject[directory].push(obj)
        return finalObject
      }, {})
    }
  }
}
</script>
