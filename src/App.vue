<template>
  <AddTodo @handle="addTask" />
  <TodoList :data="data" :removeTask="removeTask" :changeComplete="changeComplete" />
</template>

<script>
import TodoList from './components/TodoList.vue'
import AddTodo from './components/AddTodo.vue'

export default {
  components: { TodoList, AddTodo },
  data() {
    return {
      data: [
        { id: 1, title: 'Позавтракать', completed: true },
        { id: 2, title: 'Почистить огурцы', completed: false },
        { id: 3, title: 'Помыть кота', completed: true },
      ]
    }
  },
  methods: {

    removeTask(id) {
      this.data = this.data.filter((elem => elem.id !== id))
    },

    changeComplete(id) {
      this.data = this.data.map(elem => {
        if (elem.id === id) {
          elem.completed = !elem.completed
        }
        return elem
      })
    },

    addTask(title) {
      let newTodo = {
        id: Date.now(),
        completed: false,
        title
      }
      console.log(newTodo)
      this.data.push(newTodo)
    }
  }
}
</script>

<style></style>
