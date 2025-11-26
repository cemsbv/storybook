<script module>
	import { defineMeta } from '@storybook/addon-svelte-csf';
	import Button from './Button.svelte';
	import { fn } from 'storybook/test';

	const { Story } = defineMeta({
		title: 'Components/Button',
		component: Button,
		tags: ['autodocs'],
		argTypes: {
			size: {
				control: { type: 'radio' },
				options: ['sm', 'md', 'lg']
			},
			variant: {
				control: { type: 'radio' },
				options: ['primary', 'secondary', 'destructive', 'confirmative']
			},
			content: { control: 'text' }
		},
		args: {
			onclick: fn()
		}
	});
</script>

<!-- More on writing stories with args: https://storybook.js.org/docs/writing-stories/args -->
<Story name="Primary" args={{ size: 'md', variant: 'primary' }}>
	<!-- <Button {...args} /> -->
</Story>

<!-- <Story name="Secondary" args={{ label: 'Button' }} /> -->

<!-- <Story name="Large" args={{ size: 'large', label: 'Button' }} /> -->

<!-- <Story name="Small" args={{ size: 'small', label: 'Button' }} /> -->
