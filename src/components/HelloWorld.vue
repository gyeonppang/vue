<script setup lang="ts">
defineProps<{
  name: string,
  age: string
}>()
</script>

<template>
  <div class="greetings">
    <h1 class="green">{{name}}님 안녕하세요.</h1>
    <p>
      {{ name }}님의 나이는 {{ age }} 이시군요.
    </p>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
}
</style>
