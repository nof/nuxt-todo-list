<template>
  <section class="container pt-5">
    <div class="row">
      <div class="col-6">
        <div class="card">
          <div class="card-header">
            やること
          </div>
          <task-list :tasks="unfinishedTasks" />
        </div>
      </div>
      <div class="col-6">
        <div class="card">
          <div class="card-header">
            やったこと
          </div>
          <task-list :tasks="finishedTasks" />
        </div>
      </div>
    </div>
  </section>
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