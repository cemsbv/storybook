<script lang="ts">
	import { type Snippet } from 'svelte';

	export interface ButtonProps {
		variant: 'primary' | 'secondary' | 'destructive' | 'confirmative';
		size: 'sm' | 'md' | 'lg';
		disabled?: boolean;
		children: Snippet;
		onclick?: () => void;
	}
	const { variant, size, disabled, children, onclick }: ButtonProps = $props();

	// Style the button based on the variant and size props
	let buttonClass = $state('rounded-sm text-black font-md');
	if (variant === 'primary') {
		buttonClass += ' primary bg-white border border-solid border-border ';
	} else if (variant === 'secondary') {
		buttonClass += ' secondary bg-white';
	} else if (variant === 'destructive') {
		buttonClass += ' destructive text-brand-secondary border border-solid border-brand-secondary';
	} else if (variant === 'confirmative') {
		buttonClass += ' confirmative bg-brand-primary text-white border-none';
	}

	if (disabled) buttonClass += ' disabled';

	if (size === 'sm') {
		buttonClass += ' px-md py-[4px] text-sm';
	} else if (size === 'md') {
		buttonClass += ' px-lg py-sm text-sm';
	} else if (size === 'lg') {
		buttonClass += ' px-2xl py-sm text-md';
	}
</script>

<button class={buttonClass} {onclick} {disabled}>
	{@render children()}
</button>

<style lang="scss">
	button {
		&.primary {
			&:disabled {
				border-color: var(--color-bg-disabled);
				color: var(--color-bg-disabled);
				cursor: not-allowed;
			}
			&:hover:not(:disabled) {
				border-color: var(--color-spacer);
				color: var(--color-hint);
				cursor: pointer;
			}
		}
		&.secondary {
			&:disabled {
				color: var(--color-bg-disabled);
				cursor: not-allowed;
			}
			&:hover:not(:disabled) {
				color: var(--color-hint);
				cursor: pointer;
				text-decoration: underline;
			}
		}
		&.destructive {
			&:disabled {
				border-color: var(--color-bg-disabled);
				color: var(--color-bg-disabled);
				cursor: not-allowed;
			}
			&:hover:not(:disabled) {
				border-color: var(--color-brand-secondary-hover);
				color: var(--color-brand-secondary-hover);
				cursor: pointer;
			}
		}
		&.confirmative {
			&:disabled {
				background-color: var(--color-bg-disabled);
				cursor: not-allowed;
			}
			&:hover:not(:disabled) {
				background-color: var(--color-brand-primary-hover);
				cursor: pointer;
			}
		}
	}
</style>
