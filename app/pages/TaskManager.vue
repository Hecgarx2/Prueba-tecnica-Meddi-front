<script setup lang="ts">
import ListItem from '~/components/common/ListItem.vue';
import Task from '~/components/ui/tasks-item/Task.vue';

// DB
const tasks = await $fetch('http://localhost:3001/tasks')

function deleteTask(task: any) {
  console.log("delete", task)
}

function editTask(task: any) {
  console.log("edit", task)
}
</script>

<template>
  <GPageContainer>
    <template v-for="task in tasks">
      <ListItem
        @delete="deleteTask(task)"
        @edit="editTask(task)"
      >
        <Task :task="task"></Task>
      </ListItem>
    </template>
  </GPageContainer>
</template>
