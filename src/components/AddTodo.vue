<template>
    <div className='input_elem'>
        <input @keydown.enter="handle($event.target.value)" />
    </div>
</template>
  
<script>
export default {
    props: ['data'],
    methods: {
        handle(title){
            this.$emit('handle', title)
        }
    }
}
</script>
  
<style>
.input_elem {
    display: flex;
    justify-content: center;
    margin: 20px 400px;
}

.input_elem>input {
    width: 700px;
    height: 20px;
    box-shadow: 5px 5px 5px black;
    background-color: rgb(63, 63, 63);
    border: 1px solid rgb(212, 212, 212);
    border-radius: 50px;
    color: rgb(212, 212, 212);
    outline: none;
}
</style>
  