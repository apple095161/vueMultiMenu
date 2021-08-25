<template>
  <div class="hello">
    <ul>
      <dgdfg v-for="(item, index) in node" :key="index" :tree="item"> </dgdfg>
    </ul>
  </div>
</template>

<script>
import dgdfg from "./HelloWorld.vue";

export default {
  name: "menu",
  components: { dgdfg },
  data() {
    return {
      node: [
        { name: "Level1" },
        {
          name: "Level2",
          node: [
            { name: "Level3", node: [{ name: "Level3-1" }] },

            {
              name: "Level5",
              node: [{ name: "Level5-1" }],
            },
            {
              name: "Level6",
              node: [{ name: "Level6-1" }],
            },
          ],
        },
      ],
    };
  },
};
</script>


<style scoped>
</style>
