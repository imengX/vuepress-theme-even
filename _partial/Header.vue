<template>
    <div class="logo-wrapper">
        <a :href="$localePath">{{ $siteTitle }}</a> 
    </div>
</template>
<script>
export default {
    
}
</script>
<style lang="stylus" scoped>
.logo-wrapper {
  float: left;

  .logo {
    font-size: $logo-font-size;
    font-family: $logo-font-family;
  }
}
</style>
