<template>
  <v-card class="mx-auto" max-width="100%" color="rgba(255,255,255,0.5)">
    <v-container fluid>
      <v-row dense>
        <v-col v-for="card in cards" :key="card.title" :cols="card.flex">
          <v-hover v-slot="{ isHovering, props }">
            <v-card
              :href="card.ref"
              :elevation="isHovering ? 12 : 2"
              :class="{ 'on-hover': isHovering }"
              v-bind="props"
            >
              <v-img
                :src="card.src"
                class="align-end"
                gradient="to bottom, rgba(0,0,0,0.1), rgba(0,0,0,0.5)"
                height="200px"
                cover
              >
                <v-card-title
                  class="text-white text-h5"
                  v-text="card.title"
                ></v-card-title>
              </v-img>
            </v-card>
          </v-hover>
        </v-col>
      </v-row>
    </v-container>
  </v-card>
</template>

<script>
import linkedIn from "@/assets/LinkedIn.png";
import gitHub from "@/assets/GitHub.png";
import gitLab from "@/assets/GitLab.png";

export default {
  data: () => ({
    cards: [
      {
        title: "Curriculum vitae",
        src: "",
        ref: "https://cv.rjrietdijk.com",
        flex: 7,
      },
      {
        title: "LinkedIn",
        src: linkedIn,
        ref: "https://www.linkedin.com/in/rjrietdijk/",
        flex: 5,
      },
      {
        title: "Github",
        src: gitHub,
        ref: "https://www.github.com/RobinRietdijk",
        flex: 4,
      },
      {
        title: "GitLab",
        src: gitLab,
        ref: "https://www.gitlab.com/RobinRietdijk",
        flex: 4,
      },
      {
        title: "",
        src: "",
        ref: "/",
        flex: 4,
      },
    ],
  }),
};
</script>

<style scoped>
.v-card {
  opacity: 0.9;
  transition: opacity 0.2s ease-out;
}

.v-card:not(.on-hover) {
  opacity: 1;
}
</style>