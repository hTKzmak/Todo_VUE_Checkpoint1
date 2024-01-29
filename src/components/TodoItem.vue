<template>
    <div :class="[completed ? 'todo_item completed' : 'todo_item not_completed']" :id="id" @dblclick="removeTask(id)"
        @click="changeComplete(id)">
        <h1>{{ title }}</h1>
        <p>Выполнена задача: {{ completed ? 'Yes' : 'No' }}</p>
    </div>
</template>

<script>
export default {
    props: ['id', 'title', 'completed', 'removeTask', 'changeComplete'],
}
</script>

<style>
.todo_item {
    display: flex;
    flex-direction: column;
    margin: 20px 170px;
    padding: 10px;
    outline: 2px solid rgb(212, 212, 212);
    box-shadow: 5px 5px 5px black;
    transition: 0.5s;
}

.completed {
    background-color: rgb(212, 212, 212);
    color: rgb(34, 34, 34);
}

.not_completed {
    color: rgb(212, 212, 212);
    background-color: rgb(34, 34, 34);
}
</style>
