<script setup>
import { reactive, ref } from "vue";

const counter = reactive({ count: 0 });
console.log(counter.count);
counter.count++;

const message = ref("Hello World");
console.log(message.value); // Hello World
message.value = "Changed!";
</script>

<template>
  <h1>{{ message }}</h1>
  <p>Count is: {{ counter.count }}</p>
</template>
