<template>
  <div>
    <div id="hello">{{ value }}</div>
    <div>{{ message }}</div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      value: "Hello World",
      message: ""
    };
  },
  async mounted() {
    this.message = await (await fetch("/api/message?name=test")).text();
  }
};
</script>
