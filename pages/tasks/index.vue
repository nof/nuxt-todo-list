<template lang="pug">
  section.container.pt-5
    .row
      .col-6
        .card
          .card-header やること
          task-list(:tasks="unfinishedTasks")
      .col-6
        .card
          .card-header やったこと
          task-list(:tasks="finishedTasks")
</template>

<script>
import TaskList from '~/components/TaskList.vue'

export default {
  components: { TaskList },
  data() {
    return {
      tasks: [
        { id: 1, title: '牛乳を買う', finished: false },
        { id: 2, title: 'たまごを買う', finished: false },
      ]
    }
  },
  computed: {
    finishedTasks() {
      return this.tasks.filter((task) => { return task.finished })
    },
    unfinishedTasks() {
      return this.tasks.filter((task) => { return !task.finished })
    }
  },
}
</script>