<style lang="scss" scoped>
  
.footer {
  padding: 10px 20px !important;
  font-weight: 100;
  font-size: 13px;
  line-height: 20px;
  strong {
    color: #696969;
  }
}

</style>

<template lang="pug">
footer.footer
  .container
    .content.has-text-centered
      | Data last updated on <strong>{{ branding.updateTime }} (UTC)</strong>.
      br
      | Visualizations use <a href="https://github.com/d3/d3">D3</a>,
      | see the supported browsers
      | <a href="https://github.com/d3/d3/wiki#supported-environments">here</a>.
      | The <a v-bind:href="branding.sourceUrl">source</a> is licensed
      | <a href="https://opensource.org/licenses/MIT">MIT</a>.
</template>

<script>
import { mapGetters } from 'vuex'

export default {
  computed: {
    ...mapGetters(['branding'])
  }
}
</script>
