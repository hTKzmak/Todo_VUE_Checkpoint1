<template>
    <div class="todo_list" v-for="info in data">
        <TodoItem :id="info.id" :title="info.title" :completed="info.completed" :removeTask="removeTask" :changeComplete="changeComplete"/>
    </div>
</template>

<script>
import TodoItem from './TodoItem.vue'

export default {
    components: { TodoItem },
    props: [ 'data', 'removeTask', 'changeComplete' ],
}
</script>

<style></style>
