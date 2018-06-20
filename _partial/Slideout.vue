<template>
  <div>
    <div id="mobile-navbar" class="mobile-navbar">
      <div class="mobile-header-logo">
        <a :href="$localePath" class="logo">{{ $siteTitle }}</a>
      </div>
      <div class="mobile-navbar-icon">
        <span></span>
        <span></span>
        <span></span>
      </div>
    </div>
    <nav id="mobile-menu" class="mobile-menu slideout-menu">
      <a :href="key" v-for="(val, key) in menu">
        <li class="mobile-menu-item">
          {{val}}
          <!-- {% set itemName = __('menu.' + name.toLowerCase()) %} {% if itemName.startsWith('menu') %} {{ name }} {% else %} {{ itemName }} {% endif %} -->
        </li>
      </a>
    </nav>
  </div>
</template>
<script>
export default {
  props: {
    menu: Object
  }
}
</script>
