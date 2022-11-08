<script>
export default {
  name: "UserProfileComponent",
  data() {
    return {
      followers: 0,
      user: {
        id: 1,
        username: "fakudzelihle",
        firstName: "Lihle",
        lastName: "Ntolo",
        email: "lihleronaldofakudze@gmail.com",
        isAdmin: true,
        flips: [
          { id: 1, content: "flippers is not of fainted heart" },
          {
            id: 2,
            content:
              "flipper all the dushes sleeping on flippers, so flip you dush",
          },
        ],
      },
    };
  },
  methods: {
    followUser() {
      this.followers++;
    },
  },
  mounted() {
    this.followUser();
  },
  watch: {
    followers(newValue, oldValue) {
      if (newValue > oldValue) {
        console.log("New follow");
      }
    },
  },
};
</script>

<template>
  <div class="shadow-md bg-white p-2 w-min pr-10 cursor-pointer">
    <p class="text-3xl">@{{ user.username }}</p>
    <p
      class="bg-purple-900 text-white w-min rounded-md font-bold p-1 text-xs my-1"
      v-if="user.isAdmin"
    >
      Admin
    </p>
    <p class="text-sm"><strong>Followers:</strong> {{ followers }}</p>
  </div>
  <div v-for="flip in user.flips" :key="flip.id">
    <p>{{ flip.content }}</p>
  </div>
</template>
