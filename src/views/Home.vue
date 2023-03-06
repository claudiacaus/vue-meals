<template>
  <div class="flex flex-col p-8 justify-center gap-3">
    <input
      type="text"
      v-model="search"
      class="rounded border-2 border-gray-200 w-full"
      placeholder="Search for a meal..."
    />

    <div class="flex gap-2 justify-center">
      <router-link
        v-for="letter of letters"
        :key="letter"
        :to="{ name: 'byLetter', params: { letter } }"
        class="text-sm"
      >
        {{ letter }}
      </router-link>
    </div>
  </div>
</template>

<script setup>
import { computed } from "vue";
import store from "../store";

const letters = "ABCDEFGHIJKLMNOPQRSTUVWXYZ".split("");
</script>
