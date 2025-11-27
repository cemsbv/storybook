<script lang="ts">
	interface DropdownItem {
		label: string;
		value: string | number | null;
	}

	interface DropdownProps {
		size: 'sm' | 'md';
		error?: boolean;
		placeholder?: string;
		disabled?: boolean;
		value?: string | number | null;
		items: DropdownItem[];
	}
	let {
		size,
		error,
		placeholder,
		disabled,
		value = $bindable(),
		items = $bindable()
	}: DropdownProps = $props();

	let open: boolean = $state(false);
	let highlighted: number = -1;

	function select(item: DropdownItem) {
		value = item.value;
		open = false;
	}

	function toggle() {
		open = !open;
	}
</script>

<div class="dropdown relative inline-block outline-none" tabindex="-1">
	<button
		class={'trigger flex w-[200px] cursor-pointer items-center justify-between rounded-sm border border-solid border-border bg-white p-[12px] text-sm' +
			(size === 'sm' ? ' py-[8px]' : '') +
			(error ? ' border-brand-secondary outline outline-brand-secondary' : '')}
		onclick={toggle}
		{disabled}
	>
		{#if value !== null}
			{items.find((i) => i.value === value)?.label}
		{:else}
			<span class="text-border">{placeholder}</span>
		{/if}
		<span class="text-hint">
			<img src="src/lib/assets/icons/arrow-down.svg" alt="arrow down icon" />
		</span>
	</button>

	{#if open}
		<ul
			class="menu absolute top-[calc(100%+4px)] left-0 z-50 m-0 max-h-[180px] w-[200px] list-none overflow-y-auto rounded-sm border border-solid border-border bg-white p-0 shadow-lg"
		>
			{#each items as item, i}
				<li class="cursor-pointer">
					<button
						class:selected={item.value === value}
						class:highlighted={i === highlighted}
						onclick={() => select(item)}
						class="item h-full w-full cursor-pointer p-[12px] px-md text-left"
					>
						{item.label}
					</button>
				</li>
			{/each}
		</ul>
	{/if}
</div>

<style>
	li:hover,
	.highlighted {
		background: var(--color-spacer-light);
	}

	.selected {
		font-weight: 700;
	}
	.trigger:disabled {
		background: var(--color-bg-disabled);
		cursor: not-allowed;
		color: var(--color-border);
		border-color: var(--color-spacer-light);
	}
</style>
