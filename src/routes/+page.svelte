<script lang="ts">
	import Button from '$lib/components/Button/Button.svelte';
	import Input from '$lib/components/Input/Input.svelte';
	import Dropdown from '$lib/components/Dropdown/Dropdown.svelte';

	let inputVal = $state('This is input value');

	let dropdownSelected = $state(null);

	const options = [
		{ label: 'Apple', value: 'apple' },
		{ label: 'Banana', value: 'banana' },
		{ label: 'Cherry', value: 'cherry' }
	];
</script>

<div class="flex flex-col gap-lg p-2xl">
	<h1>CEMS design system</h1>
	<!-- A bunch of buttons -->
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
			<Button variant="primary" size="md" disabled>Primary</Button>
			<Button variant="secondary" size="md" disabled>Secondary</Button>
			<Button variant="destructive" size="md" disabled>Destructive</Button>
			<Button variant="confirmative" size="md" disabled>Confirmative</Button>
		</div>
	</div>

	<!-- Dropdown -->
	<div class="flex flex-col gap-md rounded-sm bg-white p-lg">
		<h2>Dropdown</h2>
		<div class="flex gap-md">
			<div>Small dropdown</div>
			<Dropdown
				size="sm"
				bind:value={dropdownSelected}
				items={options}
				placeholder="Select a fruit..."
			/>
		</div>
		<div class="flex gap-md">
			<div>Medium dropdown</div>
			<Dropdown
				size="md"
				bind:value={dropdownSelected}
				items={options}
				placeholder="Select a fruit..."
			/>
		</div>
		<div class="flex gap-md">
			<div>Disabled dropdown</div>
			<Dropdown
				size="md"
				bind:value={dropdownSelected}
				items={options}
				placeholder="Select a fruit..."
				disabled
			/>
		</div>
		<div class="flex gap-md">
			<div>Error dropdown</div>
			<Dropdown
				size="md"
				bind:value={dropdownSelected}
				items={options}
				error
				placeholder="Select a fruit..."
			/>
		</div>
	</div>

	<!-- Input fields -->
	<div class="flex flex-col gap-md rounded-sm bg-white p-lg">
		<h2>Inputs</h2>
		<div class="flex gap-md">
			<div>Small input</div>
			<Input size="sm" placeholder="Small input" />
		</div>
		<div class="flex gap-md">
			<div>Medium input</div>
			<Input size="md" placeholder="Medium input" />
		</div>
		<div class="flex gap-md">
			<div>Disabled Input</div>
			<Input size="md" placeholder="Small input" disabled />
		</div>
		<div class="flex gap-md">
			<div>Error Input</div>
			<Input size="md" placeholder="Small input" error />
		</div>
		<h2>Binding inputs to values</h2>
		<div class="flex gap-md">
			<div>Input bound to value:</div>
			<Input size="md" bind:value={inputVal} />
		</div>
		<div class="flex gap-md">
			<div>{inputVal}</div>
		</div>
	</div>
</div>
