<script>
let id = 0

export default {
  data() {
    return {
      message: 'Wahyu Afrinaldi',
      newTodo: '',
      hideCompleted: false,
      todos: [
        { id: id++, text: 'Balek Kampung', done: false }
      ]
    }
  },
  computed: {
    filteredTodos() {
      return this.hideCompleted
        ? this.todos.filter((t) => !t.done)
        : this.todos
    }
  },
  methods: {
    addTodo() {
      this.todos.push({ id: id++, text: this.newTodo, done: false })
      this.newTodo = ''
    },
    removeTodo(todo) {
      this.todos = this.todos.filter((t) => t !== todo)
    }
  }
}
</script>

<template>
  <h3>{{ message }}</h3>
  <form @submit.prevent="addTodo">
    <input v-model="newTodo" placeholder="Add TODO List">
    <button>Add Todo</button>
  </form>
  <ul>
    <li v-for="todo in filteredTodos" :key="todo.id">
      <input type="checkbox" v-model="todo.done">
      <span :class="{ done: todo.done }">{{ todo.text }}</span>
      <button @click="removeTodo(todo)"> X </button>
    </li>
  </ul>
  <button @click="hideCompleted = !hideCompleted" class="btn">
    {{ hideCompleted ? 'Show all' : 'Hide completed' }}
  </button>
</template>