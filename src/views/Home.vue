<template>
  <div class="home">
    <!-- <index-bad /> -->
    <not-index />
  </div>
</template>

<script>
// @ is an alias to /src
// import IndexBad from "@/components/IndexBad2.vue";
import NotIndex from "@/components/IndexBad.vue";

export default {
  name: "Home",
  components: {
    // IndexBad,
    NotIndex
  }
};
</script>
