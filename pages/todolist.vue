<template>
  <div class="max-w-md mx-auto bg-white shadow-lg rounded-lg overflow-hidden">
    <div class="bg-gray-200 px-6 py-4">
      <h2 class="text-lg font-bold text-gray-700 uppercase">Todo List</h2>
    </div>
    <ul v-if="todos.length > 0" class="divide-y divide-gray-300">
      <li v-for="(todo, index) in todos" :key="index" class="px-6 py-4">
        <div class="flex items-center">
          <input
            type="checkbox"
            :id="'todo' + index"
            class="h-5 w-5 text-blue-500 rounded"
            v-model="todo.completed"
          />
          <label
            :for="'todo' + index"
            class="ml-3 text-gray-700 font-medium"
            :class="{ 'line-through': todo.completed }"
            >{{ todo.text }}</label
          >
          <button
            class="ml-auto text-gray-500 hover:text-red-500"
            @click="deleteTodo(index)"
          >
            <svg class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
              <path
                fill-rule="evenodd"
                d="M6.293 6.293a1 1 0 0 1 1.414 0L10 8.586l2.293-2.293a1 1 0 1 1 1.414 1.414L11.414 10l2.293 2.293a1 1 0 0 1-1.414 1.414L10 11.414l-2.293 2.293a1 1 0 0 1-1.414-1.414L8.586 10 6.293 7.707a1 1 0 0 1 0-1.414z"
                clip-rule="evenodd"
              />
            </svg>
          </button>
        </div>
      </li>
    </ul>
    <div class="bg-gray-200 px-6 py-4">
      <form @submit.prevent="addTodo">
        <input
          type="text"
          class="w-full bg-gray-100 rounded-lg py-2 px-4 border border-gray-400"
          placeholder="Add a new task"
          v-model="newTodo"
        />
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      todos: [],
      newTodo: "",
    };
  },
  methods: {
    addTodo() {
      if (this.newTodo.trim() !== "") {
        this.todos.push({ text: this.newTodo, completed: false });
        this.newTodo = "";
      }
    },
    deleteTodo(index) {
      this.todos.splice(index, 1);
    },
  },
};
</script>
