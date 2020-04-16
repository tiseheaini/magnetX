<template>
  <div id="ad-wrap">
    <div v-html="adHtml"></div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      adHtml: String
    }
  },
  mounted () {
    this.$http.get('get-ad').then((rsp) => {
      let { html } = rsp.data
      this.adHtml = html
    })
  }
}
</script>

<style scoped>
#ad-wrap {
  padding: 0 20px 20px 20px;
}
</style>
