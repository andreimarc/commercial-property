<template>
    <div class="bc-Navbar">
      <logo></logo>
      <ul class="bc-MainMenu">
        <li class="bc-MainMenu__item" v-for="item in items" :key="item.id">
          {{ item }}
        </li>
      </ul>
    </div>
</template>

<script>
import Logo from './Logo'

// Top navbar component
export default {
  name: 'Navbar',
  data () {
    return {
      items: ['Policies', 'Claims', 'Contacts', 'Data', 'Lines', 'All Modules']
    }
  },
  components: {
    'logo': Logo
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
$background-color: #144852;
$text-color: #fff;

.bc-MainMenu {
  float: left;
  list-style-type: none;
  padding-left: 80px;
  line-height: 20px;
}

.bc-MainMenu__item {
  cursor: pointer;
  float: left;
  margin-right: 25px;

  &:hover {
    text-decoration: underline;
  }
}

.bc-Navbar {
  background: $background-color;
  color: $text-color;
  display: inline-block;
  height: 50px;
  flex: 0 1 auto;
  width: 100%;
}
</style>
