<script>
	import '../global.css';
</script>

<div>
	<!-- NAVBAR -->
	<div class='mx-10'>
		<div class='flex flex-row place-items-center gap-4 h-12 uppercase font-bold text-gray-800'>
			<div><a href="/">Home</a></div>
			<div><a href="/api/covid">Covid</a></div>
		</div>
	</div>


	<!-- BODY -->
	<div class="bg-gray-800 text-white">
		<div class="mx-10 flex flex-col">
			<div class='min-h-screen'>
				<slot />
			</div>
		</div>
	</div>

	<!-- FOOTER -->
	<div class="flex flex-row place-items-center place-content-center bg-white text-gray-800 h-12 mx-5">
			<div><a href="/">Covid Tracker</a></div>
		</div>


</div>