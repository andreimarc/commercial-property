<template>
  <h1 class="bc-Header">{{ message }}</h1>
</template>

<script>
// Simple header component
export default {
  name: 'Header',
  props: {
    message: {
      default: 'This is a header.',
      type: String
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
$primary-color: #333;

.bc-Header {
  color: $primary-color;
  display: block;
  flex: 0 1 auto;
  text-align: left;
  font-weight: 300;
  width: 95%;
  margin: 20px auto;
}
</style>
