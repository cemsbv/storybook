<script lang="ts">
	export interface InputProps {
		size: 'sm' | 'md';
		error?: boolean;
		placeholder?: string;
		disabled?: boolean;
		value?: string;
	}
	let { size, error, placeholder, disabled, value = $bindable() }: InputProps = $props();

	let inputClass = $state(
		'border-1 border-solid border-spacer-light rounded-sm text-black font-sm bg-white p-[12px] '
	);
	if (size === 'sm') {
		inputClass += ' py-sm';
	}
	if (error) inputClass += ' error';
</script>

<input class={inputClass} {placeholder} {disabled} bind:value />

<style lang="scss">
	input {
		&:focus {
			outline: solid 1px var(--color-brand-primary);
			border: solid 1px var(--color-brand-primary);
		}
		&:disabled {
			background-color: var(--color-bg-disabled);
			cursor: not-allowed;
			color: var(--color-border);
		}
		&.error {
			outline: solid 1px var(--color-brand-secondary);
			border: solid 1px var(--color-brand-secondary);
		}
	}
</style>
