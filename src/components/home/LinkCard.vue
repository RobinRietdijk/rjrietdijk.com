<template>
  <v-card
    class="mx-auto flex-container"
    max-width="60%"
    height="600px"
    color="rgba(255,255,255,0.5)"
  >
    <v-card-actions class="justify-space-between header">
      <v-btn variant="plain" icon="mdi-chevron-left" @click="prev" />
      <v-item-group v-model="onboarding" class="text-center" mandatory>
        <v-item
          v-for="window in windows"
          :key="window.title"
          v-slot="{ isSelected, toggle }"
        >
          <v-btn
            :variant="isSelected ? 'outlined' : 'text'"
            :icon="window.icon"
            @click="toggle"
          />
        </v-item>
      </v-item-group>
      <v-btn variant="plain" icon="mdi-chevron-right" @click="next" />
    </v-card-actions>

    <v-window v-model="onboarding">
      <v-window-item v-for="window in windows" :key="window.title">
        <p class="text-center">{{ window.title }}</p>
        <v-container fluid class="mt-1 py-0 content">
          <v-row dense>
            <v-col
              v-for="card in window.cards"
              :key="card.title"
              :cols="card.flex"
            >
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
                    <v-card-title class="text-white text-h5">{{
                      card.title
                    }}</v-card-title>
                  </v-img>
                </v-card>
              </v-hover>
            </v-col>
          </v-row>
        </v-container>
      </v-window-item>
    </v-window>
  </v-card>
</template>

<script>
import CV from "@/assets/CV.png";
import linkedIn from "@/assets/LinkedIn.png";
import gitHub from "@/assets/GitHub.png";
import gitLab from "@/assets/GitLab.png";

let pro_info = {
  title: "Education and experience",
  icon: "mdi-school",
  cards: [
    {
      title: "My personlised CV webpage",
      src: CV,
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
      flex: 6,
    },
    {
      title: "GitLab",
      src: gitLab,
      ref: "https://www.gitlab.com/RobinRietdijk",
      flex: 6,
    },
  ],
};

export default {
  data: () => ({
    onboarding: 0,
    windows: [pro_info],
  }),

  methods: {
    next() {
      this.onboarding =
        this.onboarding + 1 >= this.windows.length ? 0 : this.onboarding + 1;
    },

    prev() {
      this.onboarding =
        this.onboarding - 1 < 0 ? this.windows.length - 1 : this.onboarding - 1;
    },
  },
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

.v-card-actions {
  height: 15%;
}

.v-window {
  height: 85%;
}

.v-window-item {
  height: 100%;
  display: flex;
  flex-direction: column;
}

.v-container.content {
  overflow-y: auto;
  height: 100%;
  scrollbar-width: auto;
  scrollbar-color: #000000 #ffffff00;
}

.v-container.content::-webkit-scrollbar {
  width: 16px;
}

.v-container.content::-webkit-scrollbar-track {
  background: #ffffff00;
}

.v-container.content::-webkit-scrollbar-thumb {
  background-color: #424242bb;
  background-clip: content-box;
  border-radius: 10px;
  border: 4px solid #ffffff00;
}
</style>

<style>
div.v-window__container {
  height: 100%;
}
</style>