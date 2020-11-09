<template>
  <div id="app">
    
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
#app {
  font-family: Verdana, Geneva, Tahoma, sans-serif;
}

body {
	margin: 0;
	padding: 0;
	font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

* {
	box-sizing: border-box;
}

.btn-blue {
	text-align: center;
	color: white;
	margin: 5px 0;
	width: 100%;
	border-radius: 5px;
	font-size: 14px;
	border: none;
	height:36px;
	background-color: #1867C0;
	cursor: pointer;
}

.btn-primary {
	text-align: center;
	color: black;
	margin: 5px 0;
	width: 100%;
	border-radius: 5px;
	font-size: 14px;
	border: none;
	height:23px;
	background-color: #ffffff;
	border: 1px solid gainsboro;
	cursor: pointer;
}


.btn-del {
	text-align: center;
	color: white;
	margin: 5px 0;
	width: 100%;
	border-radius: 5px;
	font-size: 14px;
	border: none;
	height:23px;
	background-color: #F44336;
	cursor: pointer;
}

hr {
    border: 0.5px solid gainsboro;
    margin: 0;
}

</style>
 