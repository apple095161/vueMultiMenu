<template>
  <div class="hello">
    <ul>
      <NewMenu
        v-for="(item, index) in tableData"
        :key="index"
        :tableData="item"
      >
        <span v-if="!item.children">{{ item.name }}</span>
        <template v-else>
          <span @click="toggleShow = !toggleShow">{{ item.name }}</span>
        </template>
      </NewMenu>
    </ul>
  </div>
</template>

<script>
import NewMenu from "./HelloWorld.vue";
export default {
  name: "menu",
  components: { NewMenu },
  props: {
    tableData: {
      type: Array,
      default() {
        return [];
      },
    },
  },
  data() {
    return {
      toggleShow: false,
    };
  },
};
</script>


<style scoped>
</style>
