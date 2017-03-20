<template>
    <div>
       <h1>Home</h1>
       <p>{{msg}}</p>
    </div>
</template>

<script>
  export default {
    name: 'home',
    data () {
      return {
        msg: 'Hello, vue router'
      }
    }
  }
</script>
