<script setup lang="ts">
import { Trash2, SquarePen  } from 'lucide-vue-next';
</script>

<template>
  <div class="flex w-full border-b border-b-blue-400 shadow-xl shadow-blue-400">
    <div class="flex flex-col w-full p-2">
      <slot/>
    </div>
    <div class="flex mx-4 justify-end">
      <button class="mx-2 p-2 cursor-pointer"><SquarePen class="text-blue-400"/></button>
      <button class="mx-2 p-2 cursor-pointer"><Trash2 class="text-red-400"/></button>
    </div>
  </div>
</template>
