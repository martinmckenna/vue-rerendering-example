<!-- eslint-disable-next-line vue/valid-template-root -->
<template />

<script>
export default {
  name: "UpdateHighlighter",
  props: {},
  components: {},
  data() {
    return {
      highlightClass: "",
      highlightTimeout: undefined
    };
  },
  computed: {},
  methods: {},
  beforeDestroy() {
    clearTimeout(this.highlightTimeout);
  },
  watch: {
    $props: {
      deep: true,
      handler() {
        console.log("updated");
        this.highlightClass = "highlight";
      }
    },
    highlightClass(newVal, oldVal) {
      if (newVal && (!oldVal || oldVal === "fromWatch")) {
        this.highlightTimeout = setTimeout(() => {
          this.highlightClass = "";
        }, 1000);
      }
    }
  }
};
</script>

<style lang="scss">
.highlight {
  outline: 1px solid green;
}
</style>
