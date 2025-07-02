<template>
  <LandingPage />
  <All_Comments />
  <All_Collections />
  <TheFooter />
</template>

<script>
// @ is an alias to /src
import LandingPage from "@/components/LandingPage.vue";
import All_Comments from "@/components/All_Comments.vue";
import All_Collections from "@/components/All_Collections.vue";
import TheFooter from "@/components/TheFooter.vue";

export default {
  name: "HomeView",
  components: {
    LandingPage,
    All_Comments,
    All_Collections,
    TheFooter,
  },
};
</script>
