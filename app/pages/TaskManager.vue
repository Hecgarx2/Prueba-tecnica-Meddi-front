<script setup lang="ts">
import ListItem from '~/components/common/ListItem.vue';
import Task from '~/components/ui/tasks-item/Task.vue';

// DB
const tasks = [
  {
    id: "asdffasd",
    titulo: "Tarea1",
    descripcion: "",
    prioridad: "Alta",
    estado: "Pendiente",
    fechaVencimiento: "2026-02-27T00:00:00.000+00:00",
  },
  {
    id: "asdffasd",
    titulo: "Tarea2",
    descripcion: "AHHH",
    prioridad: "Media",
    estado: "Completado",
    fechaVencimiento: "2026-02-27T00:00:00.000+00:00",
  },
]

</script>

<template>
  <GPageContainer>
    <template v-for="task in tasks">
      <ListItem>
        <Task :task="task"></Task>
      </ListItem>
    </template>
  </GPageContainer>
</template>
