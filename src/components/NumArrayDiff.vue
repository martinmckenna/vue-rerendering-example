<template>
  <boxes
    :baseNumbers="numbers"
    :selectedNumbers="selectedNumbers"
    @click="handleClick"
  />
</template>

<script>
// import UpdateHighlighter from "../mixins/UpdateHighlighter";
import Boxes from "@/components/SelectedBoxes";
export default {
  // mixins: [UpdateHighlighter],
  name: "NumArrayDiff",
  props: {},
  components: {
    Boxes
  },
  data() {
    return {
      numbers: ["one", "two", "three"],
      selectedNumbers: []
    };
  },
  computed: {},
  methods: {
    handleClick(val) {
      if (this.selectedNumbers.includes(val)) {
        return (this.selectedNumbers = this.selectedNumbers.filter(
          e => e !== val
        ));
      }
      return (this.selectedNumbers = [
        ...new Set([...this.selectedNumbers, val])
      ]);
    }
  },
  watch: {}
};
</script>

<style lang="scss" scoped></style>
