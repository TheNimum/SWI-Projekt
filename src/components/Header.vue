<template>
<header>
<div class="headerLogo">
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/6c/Star_Wars_Logo.svg/1280px-Star_Wars_Logo.svg.png">
</div>

<div class="headerBox">
  <nav class="navbar">
	<a class="active" href="#home">Home</a>
	<a href="#people" @click="peopleView">People</a>
	<a href="#films" @click="filmView">Films</a>
	<div class=search>
	<input id="temp-name"  v-bind:property="search" placeholder="Sök" >
	<button class="people" @click="sendRequest">People</button>
	<button class="planet" @click="sendRequest2">planet</button>
	</div>
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
.headerLogo{
  border: dotted firebrick;
}
.headerLogo img{
  max-width: 20%;
}
.headerBox{
  align-content: center;
  margin: 0px;
  border:dotted Darkred;
}

.navbar a{
	float: left;
	display: block;
	color: #ffe6ff;
	text-align: center;
	padding:1em;
	text-decoration: none;
	}

/* Change the link color to (yellow)   on hover */
.navbar a:hover {
	background-image: linear-gradient(rgb(134, 120, 0), rgb(255, 238, 0));
	color: black;
	}
.search {
	padding: 1em;
	float: right;
}
.headerBox:after {
    content: "";
    display: table;
    clear: both;
}
</style>
