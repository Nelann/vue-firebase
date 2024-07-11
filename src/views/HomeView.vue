<script setup>
import { useCounterStore } from "../store/useCounterStore.js";
import { storeToRefs } from "pinia";

const store = useCounterStore();

const { count } = storeToRefs(store);
const { increment, decrement, reset } = store;
</script>

<template>
  <section class="grid place-content-center h-screen">
    <div
      class="flex flex-col items-center p-4 rounded-lg border shadow-md jutify-center w-fit"
    >
      <div class="my-6">
        <p class="text-2xl font-semibold">{{ count }}</p>
      </div>

      <div class="flex flex-row gap-3">
        <button
          class="px-4 py-2 font-semibold text-white bg-blue-500 rounded-md"
          @click="increment"
        >
          Increment
        </button>
        <button
          class="px-4 py-2 font-semibold text-white bg-rose-500 rounded-md"
          @click="reset"
        >
          Reset
        </button>
        <button
          class="px-4 py-2 font-semibold text-white bg-blue-500 rounded-md"
          @click="decrement"
        >
          Decrement
        </button>
      </div>
    </div>
  </section>
</template>
