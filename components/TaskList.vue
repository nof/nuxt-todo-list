<template>
  <ul class="list-group list-group-flush px-3">
    <li 
      v-for="task in tasks" 
      :key="task.id"
      class="list-group-item"
    >
      <input 
        :id="`task-checkbox-${task.id}`"
        v-model="task.finished" 
        class="form-check-input"
        type="checkbox" >
      <label :for="`task-checkbox-${task.id}`">
        {{ task.title }}
      </label>
    </li>
  </ul>
</template>

<script>
export default {
  props: {
    tasks: {
      type: Array,
      required: true,
      default: () => { return [] }
    }
  }
}
</script>