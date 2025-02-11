<script setup>
import { reactive, ref } from "vue";

const count = ref(0);
const increment = () => {
  count.value++;
};

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
  <button @click="increment">Count: {{ count }}</button>

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
