<template>
<header>
<div class="headerLogo">
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/6c/Star_Wars_Logo.svg/1280px-Star_Wars_Logo.svg.png">
</div>
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
.navBox{
  margin: 0px;
  border:dotted rgb(255, 251, 0);
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
	background-image: linear-gradient(rgb(105, 95, 0), rgb(255, 238, 0));
	color: black;
	}
.search {
	padding: 1em;
	float: right;
}
.navBox:after {
    content: "";
    display: table;
    clear: both;
}

</style>
