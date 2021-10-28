<template>
    <div class="mt-5">
        <form action="" class="row mb-5">
            <div class="col">
                <input type="text" class="form-control" v-model="todo.item" v-on:keyup="isDisabled" v-on:keyup.13="addTodo" placeholder="Add a new task" />
            </div>
            <div class="col-auto px-0">
                <button @click.prevent="addTodo" class="btn btn-custom" :class="disabled || btn-disabled" :disabled="disabled">Add</button>
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
            },
            disabled: true
        }
    },
    props: {
        todos: Array
    },
    methods: {
        addTodo() {
            this.todos.push({...this.todo, item: this.todo.item.trim()})
            this.todo.item = ''
            this.disabled = true
        },
        isDisabled() {
            console.log(this.todo.item)
            if(this.todo.item) {
                this.disabled = false
            } else {
                this.disabled = true
            }
        }
    }
}
</script>

<style>

</style>