<template>
  <div>
    <Header></Header>
    <h1>{{$title}}</h1>
    <h2>{{$description}}</h2>
    <!-- <div v-if="$page.frontmatter.home" v-for="page in $site.pages">
      <h2>{{page.title}}</h2>
      <p>desc</p>
    </div> -->
    <Content/>    
  </div>
</template>
 <script>
import Header from './_partial/Header.vue';

export default {
  components:{ Header },
}
</script>
