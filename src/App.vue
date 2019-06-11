<template>
  <h1 v-on:click="greet">Hello World!</h1>
</template>
<script>
  export default {
    name: 'App',
    methods: {
      greet: function () {
        if (window.Notification && Notification.permission !== "denied") {
          Notification.requestPermission(function (status) {
            var n = new Notification('通知标题', { body: '这里是通知内容！' });
          });
        }
      }
    }
  }
</script>
<style>
  html,
  body {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
    font-size: 16px;
  }
</style>