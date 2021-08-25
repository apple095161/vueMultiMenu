<template>
  <div class="hello">
    <li @click.stop="toggle">
      {{ tree.name }}
      <ul v-show="open" v-if="tree.node && tree.node.length > 0">
        <item v-for="(node, index) in tree.node" :tree="node" :key="index">
        </item>
      </ul>
    </li>
  </div>
</template>

<script>
// import item from "./myM.vue";
export default {
  // comments: { item },
  name: "item",
  props: {
    tree: {
      type: Object,
      default() {
        return {};
      },
    },
  },
  data() {
    return {
      open: false,
    };
  },
  methods: {
    toggle() {
      if (this.tree.node && this.tree.node.length > 0) {
        this.open = !this.open;
      }
    },
  },
};
</script>


<style scoped>
</style>
