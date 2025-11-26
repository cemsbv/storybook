<script lang="ts">
	import { type Snippet } from 'svelte';

	export interface ButtonProps {
		variant: 'primary' | 'secondary' | 'destructive' | 'confirmative';
		size: 'sm' | 'md' | 'lg';
		children: Snippet;
		onclick?: () => void;
	}
	let { variant, size, children, onclick }: ButtonProps = $props();

	// Style the button based on the variant and size props
	let style = $state('rounded-sm text-black font-medium');
	if (variant === 'primary') {
		style += ' bg-white border border-solid border-border ';
	} else if (variant === 'secondary') {
		style += ' bg-white';
	} else if (variant === 'destructive') {
		style += ' text-brand-secondary border border-solid border-brand-secondary';
	} else if (variant === 'confirmative') {
		style += ' bg-brand-primary text-white border-none';
	}

	if (size === 'sm') {
		style += ' px-md py-sm text-sm';
	} else if (size === 'md') {
		style += ' px-lg py-sm text-sm';
	} else if (size === 'lg') {
		style += ' px-2xl py-md text-md';
	}
</script>

<button class={style} {onclick}>
	{@render children()}
</button>
