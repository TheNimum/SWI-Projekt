<template>
<header>
<div class="headerLogo">
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/6c/Star_Wars_Logo.svg/1280px-Star_Wars_Logo.svg.png">
</div>
<<<<<<< HEAD

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
=======
>>>>>>> 18c6a1dfc485dd3c071026a4ffabbc147505c9e3
</header>
</template>

<script>          


export default {

	name: 'Header',
	data: () => ({
		search: ''
  })

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
</style>
