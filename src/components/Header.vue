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
</style>
