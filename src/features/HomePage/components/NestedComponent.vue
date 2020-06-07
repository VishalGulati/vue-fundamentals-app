<template>
  <h1>This is child component inside {{parent}}!</h1>
</template>

<script>
export default {
  // Name of the component
  name: "NestedComponent",
  props: ["parent"]
};
</script>