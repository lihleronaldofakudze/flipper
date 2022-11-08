<script>
import UserProfileComponent from "./components/UserProfileComponent.vue";
export default {
  name: "App",
  components: {
    UserProfileComponent,
  },
};
</script>

<template>
  <div class="bg-slate-50 h-screen pt-3 pl-5">
    <UserProfileComponent />
  </div>
</template>
