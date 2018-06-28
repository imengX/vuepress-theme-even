<template>
  <div>
    <SlideoutT v-bind:menu="theme.menu"></SlideoutT>
    <div class="container" id="mobile-panel">
      <Header v-bind:menu="theme.menu"></Header>
      <main id="main" class="main">
        <div class="content-wrapper">
          <div id="content" class="content">
            <div class="custom-layout" v-if="$page.frontmatter.layout">
              <component :is="$page.frontmatter.layout" />
            </div>
            <Home v-else-if="$page.frontmatter.home" />
            <Page v-else>
              <slot name="page-top" slot="top" />
              <slot name="page-bottom" slot="bottom" />
            </Page>
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
import $ from 'jquery'
import Slideout from 'slideout'
// import fancybox from 'fancybox'
import pjax from 'pjax'
import NProgress from 'nprogress'

import Header from './_partial/Header.vue'
import SlideoutT from './_partial/Slideout.vue'
import Footer from './_partial/Footer.vue'
import Home from './Home.vue'
import Page from './Page.vue'
import util from './util'

export default {
  components: {
    Header,
    SlideoutT,
    Footer,
    Home,
    Page
  },
  computed: {
    theme() {
      return this.$site.themeConfig
    }
  },
  mounted() {
    // Vue.prototype['$categories'] = this.$generateCates()
    // window.addEventListener('scroll', this.onScroll)
    // // configure progress bar
    // nprogress.configure({ showSpinner: true })
    // this.$router.beforeEach((to, from, next) => {
    //   if (to.path !== from.path && !Vue.component(to.name)) {
    //     nprogress.start()
    //   }
    //   next()
    // })
    // this.$router.afterEach(() => {
    //   nprogress.done()
    //   this.isSidebarOpen = false
    // })
  }
}
</script>

<style src="./source/css/style.scss" lang="scss"></style>
