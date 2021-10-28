<template>
    <div class="mt-5">
        <form action="" class="row mb-5">
            <div class="col">
                <input type="text" class="form-control" v-model="todo.item" placeholder="Add a new task" />
            </div>
            <div class="col-auto px-0">
                <button @click.prevent="addTodo" class="btn btn-custom">Add</button>
            </div>
        </form>
    </div>
</template>

<script>
export default {
    name: 'Form',
    data() {
        return {
            todo: {
                item: '',
                completed: false
            }
        }
    },
    props: {
        todos: Array
    },
    methods: {
        addTodo() {
            this.todos.push({...this.todo})
            this.todo.item = ''
        }
    }
}
</script>

<style>

</style>