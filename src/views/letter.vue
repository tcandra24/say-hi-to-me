<template>
  <div>
    <p class="tangerine-regular">{{ searchLetter.text }}</p>
  </div>
</template>

<script setup lang="ts">
import letterJson from "../data/letter.json";
import { ref, onMounted } from "vue";

interface Letter {
  text: string;
}

const searchLetter = ref<Letter>({});

onMounted(() => {
  searchLetter.value = letterJson[Math.floor(Math.random() * letterJson.length)];
});
</script>
