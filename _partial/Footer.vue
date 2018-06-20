<template>
  <footer id="footer" class="footer">
    <div class="copyright">
      <span class="power-by">
        <span v-html="powerby"></span>
      </span>
      <span class="division">|</span>
      <span class="theme-info">
        {{ theme }} -
        <a class="theme-link" href="https://github.com/imengX/vuepress-theme-even">Even</a>
      </span>

      <span class="copyright-year">
        <!-- {% set current = date(Date.now(), "YYYY") %} &copy; {% if theme.since and theme.since != current %} {{ theme.since }} - {% endif %} {{ current }} -->

        <span class="heart">
          <i class="iconfont icon-heart"></i>
        </span>
        <span class="author">{{ author }}</span>
      </span>
    </div>
  </footer>
</template>
<script>
export default {
  computed: {
    powerby() {
      return this.powered.replace(
        '%s',
        " <a class='hexo-link' href='https://vuepress.vuejs.org/'>VuePress</a> "
      )
    },
    powered() {
      return '由 %s 强力驱动'
    },
    theme() {
      return '主题'
    },
    author() {
      return '原文作者'
    }
  }
}
</script>
