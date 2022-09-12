<template>
  <div>{{ value }}</div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      value: "Hello World"
    };
  },
  async mounted() {
    this.value = await (await fetch("/api/message?name=test")).text();
  }
};
</script>
