<template>
  <footer id="footer" class="footer">
    <div class="copyright">
      <span class="power-by">
        <span v-html="powerby"></span>
      </span>
      <span class="division">|</span>
      <span class="theme-info">
        {{ footer.theme }} -
        <a class="theme-link" href="https://github.com/imengX/vuepress-theme-even">Even</a>
      </span>

      <span class="copyright-year">
        <!-- {% set current = date(Date.now(), "YYYY") %} &copy; {% if theme.since and theme.since != current %} {{ theme.since }} - {% endif %} {{ current }} -->

        <span class="heart">
          <i class="iconfont icon-heart"></i>
        </span>
        <span class="author">{{ footer.author }}</span>
      </span>
    </div>
  </footer>
</template>
<script>
export default {
  props: {
    footer: Object
  },
  computed: {
    powerby() {
      return this.footer.powered.replace(
        '%s',
        " <a class='hexo-link' href='https://vuepress.vuejs.org/'>VuePress</a> "
      )
    }
  }
}
</script>
