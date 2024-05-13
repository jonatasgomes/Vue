<template>
  <div>
    <input v-model="newTask" placeholder="Add new task" />
    <button @click="addTask">Add Task</button>
    <ul>
      <li v-for="task in filteredTasks" :key="task.id">
        <input type="checkbox" v-model="task.completed" />
        {{ task.text }}
      </li>
    </ul>
    <button @click="currentFilter = 'all'">All</button>
    <button @click="currentFilter = 'active'">Active</button>
    <button @click="currentFilter = 'completed'">Completed</button>
  </div>
</template>

<script>
import { ref, computed } from 'vue'

export default {
  setup() {
    const newTask = ref('');
    const tasks = ref([]);
    const currentFilter = ref('all');

    function addTask() {
      tasks.value.push({ id: tasks.value.length, text: newTask.value, completed: false })
      newTask.value = '';
    }

    const filteredTasks = computed(() => {
      if (currentFilter.value === 'all') return tasks.value;
      if (currentFilter.value === 'active') return tasks.value.filter(task => !task.completed);
      if (currentFilter.value === 'completed') return tasks.value.filter(task => task.completed);
      return '';
    });

    return { newTask, tasks, addTask, filteredTasks, currentFilter }
  }
}
</script>
