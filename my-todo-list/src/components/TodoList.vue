<template>
    <div class="centered">
        <h1>To-Do List</h1>
        <form @submit.prevent="addTodo">
            <input v-model="newTodo" placeholder="Add a new task" />
            <button type="submit">Add</button>
        </form>
        <ul>
            <li v-for="(todo, index) in todos" :key="index">
                {{ todo }}
                <button @click="removeTodo(index)">Remove</button>
            </li>
        </ul>
        <LivePreview :newTodo="newTodo" />
    </div>
</template>

<script lang="ts">
import LivePreview from './LivePreview.vue';

export default {
    components: {
        LivePreview
    },
    data() {
        return {
            newTodo: '',
            todos: [] as string[]
        };
    },
    methods: {
        addTodo() {
            if (this.newTodo.trim() !== '') {
                this.todos.push(this.newTodo.trim());
                this.newTodo = '';
            }
        },
        removeTodo(index: number) {
            this.todos.splice(index, 1);
        }
    }
};
</script>

<style scoped>
.centered {
    max-width: 500px;
    margin: 0 auto;
    padding: 20px;
    background-color: #f0f8ff;
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}

h1 {
    text-align: center;
    color: #333;
    font-family: 'Arial', sans-serif;
}

form {
    margin-bottom: 20px;
    display: flex;
    justify-content: center;
    align-items: center;
}

input {
    padding: 10px;
    margin-right: 10px;
    border-radius: 4px;
    border: 1px solid #ccc;
    flex: 1;
    max-width: 300px;
}

button {
    padding: 10px 15px;
    border-radius: 4px;
    border: none;
    background-color: #007bff;
    color: white;
    cursor: pointer;
    transition: background-color 0.3s ease;
}

button:hover {
    background-color: #0056b3;
}

ul {
    list-style-type: none;
    padding: 0;
}

li {
    background-color: #ffffff;
    margin: 5px 0;
    padding: 10px;
    border-radius: 4px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

li button {
    background-color: #dc3545;
}

li button:hover {
    background-color: #c82333;
}
</style>