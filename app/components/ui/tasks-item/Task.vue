<script setup lang="ts">
interface Task {
  id: string
  titulo: string
  descripcion: string
  prioridad: string
  estado: string
  fechaVencimiento: string
}

const { task } = defineProps<{ task: Task }>()

const formattedDate = computed(() => {
  const [year, month, day] = task.fechaVencimiento.slice(0,10).split('-');
  return `${day}/${month}/${year}`;
})
</script>

<template>
  <div class="flex flex-row w-full justify-between">
    <div class="flex flex-col">
      <h2 class="font-semibold text-xl">
        {{ task.titulo }} -
        <span class="border border-green-300 text-green-300 text-xs font-medium me-2 px-2.5 py-0.5 rounded-full">{{ task.estado }}</span>
      </h2>
      <small class="text-gray-400">{{ task.id }}</small>
    </div>

    <div class="flex items-center">
      <h4 class="text-base font-semibold">Expira: 
        <span class="font-medium">{{ formattedDate }}</span>
      </h4>
    </div>

    <div class="flex items-center">
      <span class="bg-red-900 text-red-300 border border-red-300 text-sm font-medium me-2 px-2.5 py-0.5 rounded-sm">
        {{ task.prioridad }}
      </span>
    </div>
  </div>
  <h5 class="py-2 text-sm" v-if="task.descripcion">{{ task.descripcion }}</h5>
</template>
