<script setup>
import { reactive, ref } from "vue";

const awesome = ref(true);
const toggle = () => {
  awesome.value = !awesome.value;
};

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
  <button @click="toggle">Toggle</button>
  <h1 v-if="awesome">Vue is awesome 😂</h1>
  <h1 v-else>Oh No 😘</h1>

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
/*
//2
.title {
  color: red;
}
*/
</style>
