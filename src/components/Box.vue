<template>
  <div
    @click="$emit('click', number)"
    :class="{ selected, [highlightClass]: true }"
  >
    {{ number }}
  </div>
</template>

<script>
import UpdateHighlighter from "../mixins/UpdateHighlighter";
export default {
  name: "Box",
  mixins: [UpdateHighlighter],
  props: {
    selected: Boolean,
    number: String
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

<style lang="scss" scoped>
.selected {
  color: red;
}
</style>
