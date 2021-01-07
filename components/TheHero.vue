<template>
  <section class="bg-green-700 text-white py-16">
    <div class="container mx-auto">
      <h1 class="text-4xl">サポートページ</h1>
      <h2>
        <nuxt-link :to="path">
          {{ title }}
        </nuxt-link>
      </h2>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      title: '',
      path: '',
    }
  },
  async mounted() {
    const article = await this.$content('hello').only(['title']).fetch()
    this.title = article.title
    this.path = article.path
  },
}
</script>
