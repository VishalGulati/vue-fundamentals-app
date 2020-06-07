<template>
  <button @click="$emit('new-message')">Click to send message to parent!</button>
</template>

<script>
export default {
  // Name of the component
  name: "ChildComponent"
};
</script>