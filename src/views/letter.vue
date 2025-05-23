<template>
  <div class="max-w-xl bg-[#f9f9f9] rounded-lg min-w-2xl text-center align-middle flex items-center p-5 m-5 flex-col gap-5">
    <div class="flex">
      <p class="tangerine-bold text-3xl">Quote</p>
    </div>
    <p class="tangerine-bold lg:text-[4rem] text-[2rem]">"{{ searchLetter && searchLetter.text }}"</p>
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
