<template>
  <div id="app">
    <div class="row">
      <div class="col-xs-offset-2 col-xs-8" >
        <div class="page-header">
          <h2>Rount Demo 01</h2>
        </div>
      </div>
    </div>
		<div class="row">
			<div class="col-xs-2 col-xs-offset-2">
				<div class="list-group">
          <!--<a class="list-group-item" router-link="{ path: '/home'}">Home</a>-->
					<!--<a class="list-group-item" router-link="{ path: '/about'}">About</a>-->
          <router-link class="list-group-item"  to="/home">Home</router-link>
          <router-link class="list-group-item" to="/about">About</router-link>
        </div>
      </div>
      <div class="col-xs-6">
        <div class="panel">
          <div class="panel">
            <div class="panel-body">
              <router-view></router-view>
            </div>
          </div>
        </div>
      </div>
    </div>

  

  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

body{
  background-color: #f7f8f9;
}
</style>
