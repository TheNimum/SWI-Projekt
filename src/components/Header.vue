<template>
<header>
  <div class="headerAppName">
    <h1>THE QUASAR</h1>
  </div>
  <div class="headerLogo">
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/6c/Star_Wars_Logo.svg/1280px-Star_Wars_Logo.svg.png">
  </div>
</header>
</template>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
header{
  display:grid;
  grid-template-columns: 2fr 1fr;
  background-image: linear-gradient(rgb(0, 0, 0), rgb(20, 22, 21), rgb(0, 0, 0),rgb(0, 0, 0),rgb(0, 0, 0));
  border:dotted yellow;
  border-bottom: none;
  padding: 0;
  padding-left:3em;
  margin:0;
}
.headerAppName{
  color:black;
  padding:0;
  text-align: left;
  text-shadow: -2px 0 yellow, 0 2px yellow, 2px 0 yellow, 0 -2px yellow;
  font-size: 50px;
}
.headerLogo{
  padding:0;
  padding-top: 30%;
}
.headerLogo img{
  float:right;
  max-width: 40%;
  padding:0;
  margin:0;
}
</style>
