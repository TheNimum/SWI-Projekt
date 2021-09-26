<template>
    <div class="navBox">
	<nav class="navbar">

		<a href="#people" @click="SendRequestToApp('people')">People</a>
		<a href="#films" @click="SendRequestToApp('films')">Films</a>

	<div class="searchbar">
		<input type="text" placeholder="Search..." 
			v-model="filterText" v-show="!isHidden" 
				@input="$emit('update:modelValue', $event.target.value)"/>
	</div>
  </nav>
</div>
</template>

<script>
import {ref} from "vue"
export default {

	setup() {
    const input = ref("");
    return { input };
	},

    data: () => ({
        isHidden: false
    }),

    methods: {
		SendRequestToApp(request){
			if(request==='films'){this.isHidden=true}
			else{this.isHidden=false}

			console.log('Emitting  listrequest to parent');
			this.$emit('SelectedList', request)
		},
    }
}
</script>
<style scoped>

.navBox{
	font-size: 1.5em;
	margin: 0;
	border:dotted rgb(255, 251, 0);
	background-color: black;
}
.navbar a{
	float: left;
	display: flex;
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
.searchbar {
	width:30%;
	margin: 0.5em;
	float: right;
}
input[type=text]{
	color:white;
	font-size: 70%;
	outline: none;
	border-radius: 5px;
	border: 2px outset whitesmoke;
	background:none;
	width: 90%;
	padding: 12px 20px;
	box-sizing: border-box;
}
.navBox:after {
    content: "";
    display: table;
    clear: both;
}
</style>