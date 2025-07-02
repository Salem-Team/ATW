<template>
  <TheHeader />
  <router-view />
</template>

<script>
// @ is an alias to /src
import TheHeader from "@/components/TheHeader.vue";

export default {
  name: "HomeView",
  components: {
    TheHeader,
  },
};
</script>

<style lang="scss">
:root {
  --main-color: #52057b;
}
.container {
  width: 90%;
  margin: 0px auto;
}
</style>
