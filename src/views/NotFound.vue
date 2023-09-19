<template>
  <v-container class="fill-height">
    <v-responsive class="align-center text-center fill-height">
      <message-container />

      <return-button />
    </v-responsive>
  </v-container>
</template>

<script setup>
import MessageContainer from "@/components/notfound/MessageContainer.vue";
import ReturnButton from "@/components/notfound/ReturnButton.vue";
</script>
