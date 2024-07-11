<script setup>
import { useCounterStore } from "../store/useCounterStore.js";
import { storeToRefs } from "pinia";

const store = useCounterStore();

const { count } = storeToRefs(store);
const { increment, decrement, reset } = store;
</script>

<template>
  <section>
    <div>
      <p>Ini adalah aplikasi yang dibangun dengan Vue + Pinia</p>
    </div>

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
  </section>
</template>
