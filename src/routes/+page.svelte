<script>
	import Button from '$lib/components/Button/Button.svelte';
</script>

<div class="flex flex-col gap-lg p-2xl">
	<h1>CEMS design system</h1>
	<div class="flex flex-col gap-md rounded-sm bg-white p-lg">
		<h2>Buttons</h2>
		<div class="flex gap-md">
			<Button variant="primary" size="md">Primary</Button>
			<Button variant="secondary" size="md">Secondary</Button>
			<Button variant="destructive" size="md">Destructive</Button>
			<Button variant="confirmative" size="md">Confirmative</Button>
		</div>
	</div>
</div>
