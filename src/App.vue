<script setup>
import { reactive, ref, computed, onMounted, watch } from "vue";

const todoId = ref(1);

const todoData = ref(null);

async function fetchData() {
  todoData.value = null;
  const res = await fetch(
    "https://jsonplaceholder.typicode.com/todos/${todoId.value}"
  );
  todoData.value = await res.json();
}

fetchData();
watch(todoId, fetchData);

/*
// 8. Lifecycle and Template refs
const pElementRef = ref(null);

onMounted(() => {
  pElementRef.value.textContent = "Mounted";
});
*/

/*
//7. Computed properties
let id = 0;

const newTodo = ref("");

const hideCompleted = ref(false);

const todos = ref([
  { id: id++, text: "Learn Html", done: true },
  { id: id++, text: "Learn Javascript", done: true },
  { id: id++, text: "Learn Vue", done: false },
]);

const filteredTodos = computed(() => {
  return hideCompleted.value ? todos.value.filter((t) => !t.done) : todos.value;
});

const addTodo = () => {
  todos.value.push({ id: id++, text: newTodo.value, done: false });
  newTodo.value = "";
};

const removeTodo = (todo) => {
  todos.value = todos.value.filter((t) => t !== todo);
};
*/

/*
//6. List Rendering

let id = 0;

const newTodo = ref("");

const todos = ref([
  { id: id++, text: "Learn Html" },
  { id: id++, text: "Learn Javascript" },
  { id: id++, text: "Learn Vue" },
]);

const addTodo = () => {
  // todos.value.push({ id: id++, text: newTodo.value });
  todos.value = [...todos.value, { id: id++, text: newTodo.value }];
  newTodo.value = "";
};

const removeTodo = (todo) => {
  todos.value = todos.value.filter((t) => t !== todo);
};
*/

/*
// 5. Conditional Rendering
const awesome = ref(true);
const toggle = () => {
  awesome.value = !awesome.value;
};
*/

/*
// 4. Form Binding using v-model
const text = ref("");
*/

/*
// 3. Event Listeners
const count = ref(0);
const increment = () => {
  count.value++;
};
*/

/*
// 2. Attribute Binding
const titleClass = ref("title");
*/

/* 
//1. ref and reactive
const counter = reactive({ count: 0 });
console.log(counter.count);
counter.count++;

const message = ref("Hello World");
console.log(message.value); // Hello World
message.value = "Changed!";
*/
</script>

<template>
  <p>Todo id: {{ todoId }}</p>
  <button
    @click="todoId++"
    :disabled="!todoData"
  >
    Fetch next todo
  </button>
  <p v-if="!todoData">Loading...</p>
  <pre v-else>{{ todoData }}</pre>

  <!-- 8
  <p ref="pElementRef">Hello</p>
  -->

  <!-- 7
  <form @submit.prevent="addTodo">
    <input
      v-model="newTodo"
      required
      placeholder="new todo"
    />
    <button>Add Todo</button>
  </form>
  <ul>
    <li
      v-for="todo in filteredTodos"
      :key="todo.id"
    >
      <input
        type="checkbox"
        v-model="todo.done"
      />
      <span :class="{ done: todo.done }">{{ todo.text }}</span>
      <button @click="removeTodo(todo)">X</button>
    </li>
  </ul>
  <button @click="hideCompleted = !hideCompleted">
    {{ hideCompleted ? "Show all" : "Hide completed" }}
  </button>
-->

  <!--6
  <form @submit.prevent="addTodo">
    <input
      v-model="newTodo"
      required
      placeholder="new todo"
    />
    <button>Add Todo</button>
  </form>
  <ul>
    <li
      v-for="todo in todos"
      :key="todo.id"
    >
      {{ todo.text }}
      <button @click="removeTodo(todo)">X</button>
    </li>
  </ul>
-->

  <!-- 5
  <button @click="toggle">Toggle</button>
  <h1 v-if="awesome">Vue is awesome 😂</h1>
  <h1 v-else>Oh No 😘</h1>
 -->
  <!-- 4  
  <input
    v-model="text"
    placeholder="Type here"
  />
  <p>{{ text }}</p>
 -->
  <!-- 3  
  <button @click="increment">Count: {{ count }}</button>
 -->
  <!-- 2  
  <h1 :class="titleClass">Make me red</h1>
 -->
  <!-- 1
  <h1>{{ message }}</h1>
  <p>Count is: {{ counter.count }}</p>
 -->
</template>

<style scoped>
.done {
  text-decoration: line-through;
}

/*
//2
.title {
  color: red;
}
*/
</style>
