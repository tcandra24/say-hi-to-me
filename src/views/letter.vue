<template>
  <div class="w-auto bg-[#f9f9f9] rounded-lg h-96 text-center align-middle flex items-center">
    <p class="tangerine-regular text-[4rem]">{{ searchLetter && searchLetter.text }}</p>
  </div>
</template>

<script setup lang="ts">
import letterJson from "../data/letter.json";
import { ref, onMounted } from "vue";

interface Letter {
  text: string;
}

const searchLetter = ref<Letter>();

onMounted(() => {
  searchLetter.value = letterJson[Math.floor(Math.random() * letterJson.length)];
});
</script>
