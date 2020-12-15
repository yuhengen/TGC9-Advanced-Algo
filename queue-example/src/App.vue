<template>
  <div id="app">
    <QueueExample />
    <Animation />
  </div>
</template>

<script>
import QueueExample from "./components/QueueExample";
import Animation from "./components/Animation";

export default {
  name: "App",
  components: {
    QueueExample,
    Animation,
  },
};
</script>

<style>
</style>
