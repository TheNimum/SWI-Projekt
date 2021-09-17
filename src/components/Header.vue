<template>
  <header class="page-header">
    <p>Header</p>
  </header>
    <nav class="navbar">
    <a class="active" href="#home">Home</a>
    <a href="#people">People</a>
    <a href="#films">Films</a>
  </nav>

</template>

<script>
export default {
  name: 'Header',
  props:{
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.page-header{
  
  margin: 0px;
  border:dotted Darkred;
}

.navbar a {
	float: left;
	}

.navbar a {
	display: block;
	color: #ffe6ff;
	text-align: center;
	padding: 14px 16px;
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
