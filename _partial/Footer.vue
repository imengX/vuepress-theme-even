<template>
  <footer id="footer" class="footer">
    <div class="copyright">
      <span class="power-by">
        <span v-html="powerby"></span>
      </span>
      <span class="division">|</span>
      <span class="theme-info">
        {{ theme.footer.theme }} -
        <a class="theme-link" href="https://github.com/imengX/vuepress-theme-even">Even</a>
      </span>

      <span class="copyright-year">
        {{copyrightYear}}
        <span class="heart">
          <i class="iconfont icon-heart"></i>
        </span>
        <span class="author">{{ theme.copyright.author }}</span>
      </span>
    </div>
  </footer>
</template>
<script>
export default {
  props: {
    theme: Object
  },
  computed: {
    powerby() {
      return this.theme.footer.powered.replace(
        '%s',
        " <a class='hexo-link' href='https://vuepress.vuejs.org/'>VuePress</a> "
      )
    },
    copyrightYear() {
      var now = new Date().getFullYear()
      var temp = ''
      var theme = this.theme
      if (theme.since && theme.since != now) {
        temp = theme.since + ' - '
      }
      temp += now
      return temp
    }
  }
}
</script>
