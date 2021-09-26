<template>
<footer>
	<div class="footerDescription">
		<div class="left">
			<h2>The Quasar</h2>
			<p>Kurs: Utveckling av webbapplikationer</p>
			<p>Klass: Systemutvecklare .NET 4</p>
			<p>Termin: HT 2021</p>
		</div>
		<div class="right">
			<p>Syftet med skapandet av appen "The Quasar" är att träna på teknikerna som används för att 
				bygga moderna webbappar, samt att ge kunskaper för att underlätta vår
				fortsatta utveckling inom området. Att jobba med webbapplikationer</p>
			<h3> Appen ska kunna:</h3> 
			<p>Hämta en lista med alla personer och filmer från API </p>
			<p>Filtrera listan av personer genom inmatning från användare</p>
		</div>
	</div>

</footer>
</template>

<script>

export default ({
	data: () => ({

	}),
})
</script>

<style scoped>
footer{
	color: white;
	border: dotted yellow;
	border-top: none;
	background-image: linear-gradient(rgb(0, 0, 0),rgb(0, 0, 0), rgb(20, 22, 21));
	padding:1.5em;
	margin:0;
}
.footerDescription{
	display:grid;
	grid-template-columns: 1fr 1fr;
}
.left{
	text-align: left;
	justify-self: start;
	padding-left: 1.5em;
}


</style>
