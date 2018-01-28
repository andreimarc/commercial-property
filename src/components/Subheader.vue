<template>
  <h2 class="bc-Subheader">{{ message }}</h2>
</template>

<script>
// h2 headers
export default {
  name: 'Subheader',
  props: {
    message: {
      default: 'This is a subheader.',
      type: String
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
.bc-Subheader {
  display: block;
  text-align: left;
}
</style>
