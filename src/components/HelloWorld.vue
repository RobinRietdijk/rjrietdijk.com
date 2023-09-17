<template>
  <v-container class="fill-height">
    <v-responsive class="align-center fill-height">
      <v-img height="300" src="@/assets/logo.png" />

      <div class="text-body-2 font-weight-light mb-n1 text-center">
        Welcome to
      </div>

      <h1 class="text-h2 font-weight-bold text-center">RJRietdijk.com</h1>

      <div class="py-14" />

      <v-card class="mx-auto" max-width="100%">
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
    </v-responsive>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    cards: [
      {
        title: "Pre-fab homes",
        src: "https://cdn.vuetifyjs.com/images/cards/house.jpg",
        ref: "https://google.com",
        flex: 4,
      },
      {
        title: "Favorite road trips",
        src: "https://cdn.vuetifyjs.com/images/cards/road.jpg",
        ref: "https://google.com",
        flex: 4,
      },
      {
        title: "Best airlines",
        src: "https://cdn.vuetifyjs.com/images/cards/plane.jpg",
        ref: "https://google.com",
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
