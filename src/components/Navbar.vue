<template>
    <div class="navBox">
	<nav class="navbar">
		<!-- <a class="active" href="#home" @click="SendRequestToApp('home')">Home</a> -->
		<a href="#people" @click="SendRequestToApp('people')">People</a><!--Ändra till Sant/falskt-->
		<a href="#films" @click="SendRequestToApp('films')">Films</a>

	<div class="searchbar">
		<input type="text" placeholder="Search..." v-model="filterText" v-show="!hiddenSearchBar" @input="$emit('update:modelValue', $event.target.value)"/>
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
		hiddenSearchBar: false,
    }),

    methods: {
		SendRequestToApp(request){
			if(request === 'films')
			{
			this.hiddenSearchBar = true
			}else
			this.hiddenSearchBar = false;
			console.log('Emitting  listrequest to parent');
			// emit ( namnet på funktionen, data som ska skickas )
			this.$emit('SelectedList', request)
		},
    }
}
</script>
<style scoped>


</style>