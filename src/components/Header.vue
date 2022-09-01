<script setup>
  defineProps(['color'])
</script>

<template>
  <header>
    <h1 :style="{'color': color}"><slot></slot></h1>
  </header>
</template>