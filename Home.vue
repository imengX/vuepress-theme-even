<template>
  <section id="posts" class="posts">
    <div
      class="nav-item"
      v-for="page in $site.pages"
      >
      <PostTemplate v-bind:post="page" v-if="!page.frontmatter.home"/>
    </div>

    <!-- {% for post in  %}
      {{ post_template.render(post) }}
    {% endfor %} -->
  </section>
</template>

<script>
import PostTemplate from './_macro/post.vue'

export default {
  components: { PostTemplate },
  computed: {
    data () {
      return this.$page.frontmatter
    },
    actionLink () {
      return {
        link: this.data.actionLink,
        text: this.data.actionText
      }
    }
  }
}
</script>