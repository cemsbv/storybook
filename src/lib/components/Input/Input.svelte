<script lang="ts">
	export interface InputProps {
		size: 'sm' | 'md';
		error?: boolean;
		placeholder?: string;
		disabled?: boolean;
	}
	const { size, error, placeholder, disabled }: InputProps = $props();

	let inputClass = $state(
		'border border-solid border-spacer-light rounded-sm text-black font-sm bg-white p-[12px] '
	);
	if (size === 'sm') {
		inputClass += ' py-sm';
	}
	if (error) inputClass += ' error';
</script>

<input class={inputClass} {placeholder} {disabled} />

<style lang="scss">
	input {
		&.error {
			border: solid 1px var(--color-brand-secondary);
		}
		&:focus:not(.error) {
			outline: none;
			border: solid 1px var(--color-brand-primary);
		}
		&:disabled {
			background-color: var(--color-bg-disabled);
			cursor: not-allowed;
			color: var(--color-border);
		}
		&:focus.error {
			outline: none;
			border: solid 1px var(--color-brand-secondary);
		}
	}
</style>
