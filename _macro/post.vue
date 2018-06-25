<template>
    <article class="post">
    <header class="post-header">
      <h1
       v-if="$page.frontmatter.home"
       class="post-title">
          <a class="post-link" :href="post.path">{{ post.title }}</a>
      </h1>
      <h1 v-else>
        {{ post.title }}
      </h1>

      <div class="post-meta">
        <span class="post-time">
            {{date}}
        </span>
      </div>
    </header>
  </article>
</template>
<script>
export default {
  props: {
    post: Object
  },
  computed:{
    date () {
        if (this.post.lastUpdated) {
         var theDate = new Date(this.post.lastUpdated);
         return theDate.toLocaleDateString();
        }
        return null;
    }
  }
}
</script>
