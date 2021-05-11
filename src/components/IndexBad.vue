<template>
  <div>
    <div class="flex-wrapper">
      <div>
        <team-item v-for="item in footballArray" :key="item" :label="item" />
        <button @click="handleClick">Remove First</button>
      </div>
      <div>
        <team-item
          v-for="(item, index) in baseballArray"
          :key="index"
          :label="item"
        />
        <button @click="handleClick2">Remove First</button>
      </div>
    </div>
    <button class="restore-btn" @click="handleRestore">Restore</button>
  </div>
</template>

<script>
import TeamItem from "./TeamItem";

export default {
  name: "IndexBad",
  props: {},
  components: {
    TeamItem
  },
  data() {
    return {
      footballArray: ["Eagles", "Colts", "Steelers", "Jets"],
      baseballArray: ["Phillies", "Rays", "Yankees", "Pirates"]
    };
  },
  computed: {},
  methods: {
    handleClick() {
      this.footballArray = this.footballArray.slice(
        1,
        this.footballArray.length
      );
    },
    handleClick2() {
      this.baseballArray = this.baseballArray.slice(
        1,
        this.baseballArray.length
      );
    },
    handleRestore() {
      this.footballArray = ["Eagles", "Colts", "Steelers", "Jets"];
      this.baseballArray = ["Phillies", "Rays", "Yankees", "Pirates"];
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

button {
  height: 50px;
  width: 100px;
  margin-top: 20px;

  &.restore-btn {
    margin-top: 100px;
  }
}
</style>
