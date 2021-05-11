<template>
  <div class="flex-wrapper">
    <div :class="highlightClass" v-for="(array, index) in arrays" :key="index">
      <team-item v-for="item in array" :key="item" :label="item" />
      <button @click="index === 0 ? handleClick() : handleClick2()">
        Remove First
      </button>
    </div>
  </div>
</template>

<script>
import TeamItem from "./TeamItem";
import UpdateHighlighter from "../mixins/UpdateHighlighter";

export default {
  name: "IndexBad",
  mixins: [UpdateHighlighter],
  props: {},
  components: {
    TeamItem
  },
  data() {
    return {
      arrays: [
        ["Eagles", "Colts", "Steelers", "Jets"],
        ["Phillies", "Rays", "Yankees", "Pirates"]
      ]
    };
  },
  computed: {},
  methods: {
    handleClick2() {
      this.arrays = [
        this.arrays[0],
        this.arrays[1].slice(1, this.arrays[1].length)
      ];
    },
    handleClick() {
      this.arrays = [
        this.arrays[0].slice(1, this.arrays[0].length),
        this.arrays[1]
      ];
    }
  },
  watch: {}
};
</script>

<style lang="scss" scoped>
.flex-wrapper {
  display: flex;
  flex-flow: row;
  justify-content: space-evenly;
  margin-top: 100px;
}
</style>
