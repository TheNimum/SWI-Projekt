<template>
    <div class="navBox">
	<nav class="navbar">
		<a class="active" href="#home" @click="SendRequestToApp('home')">Home</a>
		<a href="#people" @click="SendRequestToApp('people')">People</a><!--Ändra till Sant/falskt-->
		<a href="#films" @click="SendRequestToApp('films')">Films</a>
	
	<div class="searchbar">
		<input type="text" placeholder="Search..." v-model="filterText" @input="$emit('update:modelValue', $event.target.value)"/>
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
        request:'',
    }),

    methods: {
		SendRequestToApp(request){
			console.log('Emitting  listrequest to parent');
			// emit ( namnet på funktionen, data som ska skickas )
			this.$emit('SelectedList', request)
		},
    }   
}
</script>
<style scoped>

.navBox{
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
/* Style the "active" element to highlight the current page */
/*.navbar a.active {
  background-image: linear-gradient(rgb(105, 95, 0), rgb(255, 238, 0));
  color: black;
}*/
.searchbar {
	padding: 1em;
	float: right;
}
.navBox:after {
    content: "";
    display: table;
    clear: both;
}
</style>