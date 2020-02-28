<template>
  <div>
    
  </div>
</template>

<script>

export default {
  name: 'App',
  components: {
  },
  data: () => {
    return {
      todos: [{
        id: '1',
      text: 'todo one',
      completed: false
    }, {
      id: '2',
      text: 'todo two',
      completed: true
    }]
    }
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
