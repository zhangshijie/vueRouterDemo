<template>
  <div>
    <div>
       <h1>Home</h1>
       <p>{{msg}}</p>
    </div>
    <div>
      <ul class="nav nav-tabs">
        <li>
          <router-link :to="{path: '/home/message'}" >Message</router-link>
        </li>
        <li>
          <router-link :to="{path: '/home/news'}" >News</router-link>
        </li>
      </ul>
      <router-view></router-view>
    </div>
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
