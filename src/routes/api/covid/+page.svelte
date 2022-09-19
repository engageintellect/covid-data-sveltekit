<script lang='typescript'>
	// GLOBAL VARS
	let response: any = null;
	let california: object;
	let data = {};

	// API KEY
	const apiKey = 'a3615cb1f54942ba867f9fa661d69a83'

	// FETCH API
	const getData = async () => {
		const res = await fetch(`https://api.covidactnow.org/v2/states.json?apiKey=${apiKey}`);
		response = await res.json();
		california = response[4];
		console.log(california)

		// STRUCTURE RESULTS
		data = {
			country: response[4].country,
			state: response[4].state,
			population: response[4].population,
			cases: response[4].actuals.cases,
			deaths: response[4].actuals.deaths,
			positive_tests: response[4].actuals.positiveTests,
			negative_tests: response[4].actuals.negativeTests,
			contact_tracers: response[4].actuals.contactTracers,
			new_cases: response[4].actuals.newCases,
			new_deaths: response[4].actuals.newDeaths,
		}
	}

	getData();
</script>


<!-- MAIN COMPONENT -->

<div class="my-10">
	<div class="text-6xl font-bold">Results</div>

	<div class="my-5">
		<table class="w-1/3">
			{#if data != ''}
				{#each Object.entries(data) as [x, y]}
					<tr>
						<td>{x.toUpperCase()}</td>
						<td>{y}</td>
					</tr>
				{:else}
					<h3><strong>Loading data from API...</strong></h3>
				{/each}
			{/if}
		</table>
	</div>
</div>


<!-- STYLE -->
<style>
	td {
  border: 1px solid;
	padding: .5rem;
}
</style>

