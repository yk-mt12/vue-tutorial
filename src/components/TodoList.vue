<script setup>
  defineProps(['todos'])
  const emit = defineEmits(['removeTodo'])

  const clickRemove = (i) => emit('removeTodo', i)
</script>

<template>
  <!-- v-showなら要素がないときに, display: noneで非表示に -->
  <ul v-if="todos.length > 0">
    <li v-for="(todo, i ) in todos" v-bind:key="i">
      {{todo}} <span @click="clickRemove(i)" style="cursor: pointer">x</span>
    </li>
  </ul>
  <p v-else> ※ Todoを追加してください</p>
</template>