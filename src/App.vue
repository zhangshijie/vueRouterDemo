<template>
  <div id="app">
    <div class="row">
      <div class="col-xs-offset-2 col-xs-8" >
        <div class="page-header">
          <h2>Rount Demo 04</h2>
        </div>
      </div>
    </div>
		<div class="row">
			<div class="col-xs-2 col-xs-offset-2">
				<div class="list-group">
          <!--<a class="list-group-item" router-link="{ path: '/home'}">Home</a>-->
					<!--<a class="list-group-item" router-link="{ path: '/about'}">About</a>-->
          <router-link class="list-group-item"  to="/home" >Home</router-link>
          <router-link class="list-group-item" to="/about" >About</router-link>
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

    <div class="row">
			<div class="col-xs-offset-2 col-xs-8">
				<div class="well">
					<p>当前路径：<code>{{$route.path}}</code></p>
					<p>当前参数：<code>{{$route.params | json}}</code></p>
					<p>路由名称：<code>{{$route.name}}</code></p>
					<p>路由查询参数：<code>{{$route.query | json}}</code></p>
					<!--<p>路由匹配项：<code>{{$route.matched | json}}</code></p>-->
				</div>
			</div>
		</div>


     <div class="row">
       	<div class="col-xs-offset-2 col-xs-8">
        <h1>{{ msg }}</h1>
        <ul>
          <li v-for="article in articles">
            
              <div class="m-img inl-block"><img v-bind:src="article.images.small"/></div>
              <div class="m-content inl-block">
              <div>{{article.title}}</div>
                <div>年份：{{article.year}}</div>
                <div>类型：{{article.subtype}}</div>
              </div>
          </li>
        </ul>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'app',
  data (){
    return{
      msg: '豆瓣api',
      articles:[]
    }
  },
  created:function(){
      this.$http.jsonp('https://api.douban.com/v2/movie/top250?count=10',{},{
        header:{},
        emulateJSON:true
      }).then(function(response){
        console.log(response)
        this.articles = response.data.subjects
      },function(response){
        console.log(response)
      });

    // this.$http.jsonp('https://api.douban.com/v2/movie/top250?count=10', {}, {
    //     headers: {
 
    //     },
    //     emulateJSON: true
    // }).then(function(response) {
    //   // 这里是处理正确的回调
 
    //     this.articles = response.data.subjects
    //     // this.articles = response.data["subjects"] 也可以
 
    // }, function(response) {
    //     // 这里是处理错误的回调
    //     console.log(response)
    // });
  }
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
