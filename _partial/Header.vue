<template>
  <header id="header" class="header">
    <div class="logo-wrapper">
      <a :href="$localePath" class="logo">{{ $siteTitle }}</a>
    </div>
    <nav class="site-navbar">
      <ul id="menu" class="menu" v-if="menu">
        <!-- {% for name, path in theme.menu %} -->
        <li class="menu-item" v-for="(val, key) in menu">
          <!-- <a class="menu-item-link" href="{{ url_for(item.path) }}"> -->
          <a class="menu-item-link" :href="key">
            {{val}}
            <!-- {% set itemName = __('menu.' + name.toLowerCase()) %} {% if itemName.startsWith('menu') %} {{ name }} {% else %} {{ itemName }} {% endif %} -->
          </a>
        </li>
      </ul>
    </nav>
  </header>
</template>
<script>
export default {
  props: {
    menu: Object
  }
  // computed: {
  //   menu() {
  //     return this.$site.themeConfig.menu
  //   }
  // }
}
</script>
