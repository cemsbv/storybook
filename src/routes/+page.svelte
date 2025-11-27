<script>
	import Button from '$lib/components/Button/Button.svelte';
</script>

<div class="flex flex-col gap-lg p-2xl">
	<h1>CEMS design system</h1>
	<div class="flex flex-col gap-md rounded-sm bg-white p-lg">
		<h2>Buttons</h2>
		<div class="flex gap-md">
			<div>Small buttons</div>
			<Button variant="primary" size="sm">Primary</Button>
			<Button variant="secondary" size="sm">Secondary</Button>
			<Button variant="destructive" size="sm">Destructive</Button>
			<Button variant="confirmative" size="sm">Confirmative</Button>
		</div>
		<div class="flex gap-md">
			<div>Medium butons</div>
			<Button variant="primary" size="md">Primary</Button>
			<Button variant="secondary" size="md">Secondary</Button>
			<Button variant="destructive" size="md">Destructive</Button>
			<Button variant="confirmative" size="md">Confirmative</Button>
		</div>
		<div class="flex gap-md">
			<div>Large butons</div>
			<Button variant="primary" size="lg">Primary</Button>
			<Button variant="secondary" size="lg">Secondary</Button>
			<Button variant="destructive" size="lg">Destructive</Button>
			<Button variant="confirmative" size="lg">Confirmative</Button>
		</div>
		<div class="flex gap-md">
			<div>Disabled butons</div>
			<Button variant="primary" size="md" disabled={true}>Primary</Button>
			<Button variant="secondary" size="md" disabled={true}>Secondary</Button>
			<Button variant="destructive" size="md" disabled={true}>Destructive</Button>
			<Button variant="confirmative" size="md" disabled={true}>Confirmative</Button>
		</div>
	</div>
</div>
