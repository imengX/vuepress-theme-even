<template>
  <div>
    <Slideout v-bind:menu="theme.menu"></Slideout>
    <div class="container" id="mobile-panel">
      <Header v-bind:menu="theme.menu"></Header>
      <main id="main" class="main">
        <div class="content-wrapper">
          <div id="content" class="content">
            <Content/>
          </div>
          <!-- {% include '_partial/comments.swig' %} -->
        </div>
      </main>
      <Footer v-bind:footer="theme.footer"></Footer>
      <div class="back-to-top" id="back-to-top">
        <i class="iconfont icon-up"></i>
      </div>
    </div>
  </div>
</template>
 <script>
import Header from './_partial/Header.vue'
import Slideout from './_partial/Slideout.vue'
import Footer from './_partial/Footer.vue'

export default {
  components: { Header, Slideout, Footer },
  computed: {
    theme() {
      return this.$site.themeConfig
    }
  }
}
</script>

<style src="./source/css/style.scss" lang="scss"></style>
