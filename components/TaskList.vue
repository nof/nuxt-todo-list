<template lang="pug">
  ul.list-group.list-group-flush.px-3
    li.list-group-item(v-for="task in tasks" :key="task.id")
      input.form-check-input(:id="`task-checkbox-${task.id}`" v-model="task.finished" type="checkbox")
      label(:for="`task-checkbox-${task.id}`") {{ task.title }}
</template>

<script>
export default {
  props: {
    tasks: {
      type: Array,
      required: true
    }
  }
}
</script>