<template>
  <div class="bc-Tags">
    <bc-subheader message="Tags" style="font-size: 16px;"></bc-subheader>
    <div class="bc-Tags__tab">
      <h4 class="bc-Tags__subheader">Tag group</h4>
      <ul class="bc-Tags__list">
        <li class="bc-Tags__list-item" v-for="group in tag_groups" :key="group.id">
          <button class="bc-Tags__btn" type="button" v-on:click="selectTagGroup(group)">{{ group.title }}</button>
        </li>
      </ul>
    </div>
    <div class="bc-Tags__tab">
      <h4 class="bc-Tags__subheader">Tags</h4>
      <div class="bc-Tags__placeholder" v-if="tags.length === 0">Select a tag group to see individual tags</div>
      <ul class="bc-Tags__list">
        <li class="bc-Tags__list-item" v-for="tag in tags" :key="tag.id">
          <select-tag-button class="bc-Tags__btn" v-bind:tag="tag"></select-tag-button>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import Subheader from './Subheader'
import SelectTagButton from './SelectTagButton'

// The tags section under the form
export default {
  name: 'Tags',
  data () {
    return {
      tag_groups: [
        {
          title: 'Vinmaster',
          tags: ['Car make', 'Car model', 'Year built', 'Miles']
        },
        {
          title: 'ISO',
          tags: ['Apples', 'Pears', 'Pineapples', 'Bananas']
        },
        {
          title: 'Tag 3',
          tags: ['Cats', 'Leopards', 'Pumas', 'Tigers']
        }
      ],
      tags: [],
      isActive: false
    }
  },
  props: ['groups'],
  components: {
    'bc-subheader': Subheader,
    'select-tag-button': SelectTagButton
  },
  methods: {
    selectTagGroup: function (group) {
      this.tags = group.tags
    },
    selectTag: function () {
      this.isActive = !this.isActive
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
.bc-Tags {
  float: left;
  width: 100%;
  text-align: left;
}

.bc-Tags__subheader {
  font-size: 13px;
}

.bc-Tags__tab {
  width: 50%;
  float: left;
}

.bc-Tags__placeholder {
  font-size: 12px;
  font-style: italic;
}

.bc-Tags__list {
  padding: 0;
}

.bc-Tags__list-item {
  display: inline;
}

.bc-Tags__btn {
  background: #eff4f5;
  border: 1px solid rgba(131, 169, 175, .3);
  border-radius: 3px;
  color: #017c91;
  cursor: pointer;
  font-weight: bold;
  margin-right: 5px;
  outline: 0;

  &:hover {
    background: #c6d9dd;
  }
}

.bc-Tags__btn--active {
  background: #017c91;
  color: #eff4f5;
}
</style>
