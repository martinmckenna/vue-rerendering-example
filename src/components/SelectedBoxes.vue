<template>
  <div>
    <input type="text" v-model="text" />
    <div v-for="number in baseNumbers" :key="number">
      <box
        @click="handleClick"
        :selected="selectedNumbers.includes(number)"
        :number="number"
      />
    </div>
  </div>
</template>

<script>
import Box from "@/components/Box";
export default {
  name: "SelectedBoxes",
  props: {
    selectedNumbers: Array,
    baseNumbers: Array
  },
  components: {
    Box
  },
  data() {
    return {
      text: ""
    };
  },
  computed: {},
  methods: {
    handleClick(val) {
      this.$emit("click", val);
    }
  },
  watch: {
    text(newVal) {
      console.log(newVal);
    }
  }
};
</script>

<style lang="scss" scoped></style>
