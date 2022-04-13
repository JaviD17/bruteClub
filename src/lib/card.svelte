<script>
	let names = 'Javi';
	let title = "this title";
</script>

<div class="card">
	<slot name="names" {names}>Slot Fallback</slot>
	<slot name="title" {title}>Slot Fallback</slot>
</div>

<style>
	.card {
		width: 150px;
		padding: 1em;
		margin: 0 0 1em 0;
	}
	.card-bdr {
		border: 1px solid #aaa;
		box-shadow: 2px 2px 8px rgba(0, 0, 0, 0.1);
	}
</style>
