<template>
<header>
<div class="testX">
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/6c/Star_Wars_Logo.svg/1280px-Star_Wars_Logo.svg.png">
</div>

<div class="headerBox">
  <nav class="navbar">
	<a class="active" href="#home">Home</a>
	<a href="#people">People</a>
	<a href="#films">Films</a>
	<input id="temp-name"  v-bind:search="search" placeholder="Sök" >
	<button class="people" @click="sendRequest(search)">People</button>
	<button class="planet" @click="sendRequest2(search)">planet</button>
	
  </nav>
  </div>
</header>
</template>

<script>          


export default {
  
  name: 'Header',
  data: () => ({search: ''}) 
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.testX{
  border: dotted firebrick;
}
.testX img{
  max-width: 20%;
}
.headerBox{
  padding: 14px 16px;
  align-content: center;
  margin: 0px;
  border:dotted Darkred;
}

.navbar a{
  float: left;
	display: block;
	color: #ffe6ff;
	text-align: center;
	padding-left:1em;
	text-decoration: none;
	}

/* Change the link color to (rgb(0, 134, 22) (green)   on hover */
.navbar a:hover {
	background-image: linear-gradient(rgb(134, 120, 0), rgb(255, 238, 0));
	color: black;
	}
  .main:after {
    content: "";
    display: table;
    clear: both;
}
</style>
