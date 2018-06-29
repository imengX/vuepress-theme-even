<template>
  <article class="post">
    <header class="post-header">
      <h1 v-if="$page.frontmatter.home" class="post-title">
        <a class="post-link" :href="post.path">{{ post.title }}</a>
      </h1>
      <h1 v-else>
        {{ post.title }}
      </h1>

      <div class="post-meta">
        <span class="post-time">
          {{lastUpdated}}
        </span>

        <div v-if="categories && categories.length" class="post-category">
          <a v-for="category in categories" :href="category">
            {{ category }}
          </a>
        </div>
      </div>
    </header>
  </article>
</template>
<script>
export default {
  props: {
    post: Object
  },
  computed: {
    lastUpdated() {
      var lastUpdated = this.$page.lastUpdated
      var val = lastUpdated ? new Date(this.$page.lastUpdated) : new Date()

      return val.toLocaleString(this.$lang)
    },
    categories() {
      var category = this.post.frontmatter.category
      var val = null
      if (typeof category === 'string') {
        val = [category]
      }
      if (category instanceof Array) {
        val = category
      }

      console.log(typeof category)

      console.log(category)
      console.log(val)
      return val
    }
  }
}
</script>
