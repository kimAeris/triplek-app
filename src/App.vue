<template>
  <NavBar />
  <Profile />
  <Application />
</template>

<script>
import NavBar from "/@/components/NavBar.vue";
import Profile from "/@/components/Profile.vue";
import Application from "/@/components/Application.vue";

export default {
  name: "App",
  components: {
    NavBar,
    Profile,
    Application,
  },
};
</script>
