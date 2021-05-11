<template>
  <div :class="highlightClass">{{ label }}</div>
</template>

<script>
import UpdateHighlighter from "../mixins/UpdateHighlighter";
export default {
  name: "TeamItem",
  mixins: [UpdateHighlighter],
  props: {
    label: String
  },
  components: {},
  data() {
    return {};
  },
  computed: {},
  methods: {},
  watch: {}
};
</script>

<style lang="scss" scoped></style>
