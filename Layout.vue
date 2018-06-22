<template>
  <div>
    <SlideoutT v-bind:menu="theme.menu"></SlideoutT>
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
      <Footer v-bind:theme="theme"></Footer>
      <div class="back-to-top" id="back-to-top">
        <i class="iconfont icon-up"></i>
      </div>
    </div>
  </div>
</template>
 <script>
import $ from "jquery";
import Slideout from 'slideout'
// import fancybox from 'fancybox'
import pjax from 'pjax'
import NProgress from 'nprogress'

import Header from './_partial/Header.vue'
import SlideoutT from './_partial/Slideout.vue'
import Footer from './_partial/Footer.vue'

export default {
  components: { Header, SlideoutT, Footer },
  computed: {
    theme() {
      return this.$site.themeConfig
    }
  }
}
</script>

<style src="./source/css/style.scss" lang="scss"></style>
