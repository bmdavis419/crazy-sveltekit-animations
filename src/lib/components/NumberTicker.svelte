<script lang="ts">
	import { cubicOut } from 'svelte/easing';
	import { onMount } from 'svelte';
	import { spring, tweened } from 'svelte/motion';
	import { cn } from '$lib/utils';

	import { inview } from 'svelte-inview';

	export let value = 100;
	export let initial = 0;
	export let duration = 6000;

	export let inViewMargin = '-50px';

	export let once = false;

	let isInView = 'hidden';

	let num = tweened(initial, {
		duration: duration,
		easing: cubicOut
	});
	let className: any = '';
	export { className as class };

	$: if (isInView === 'visible') {
		num.set(value);
	}
</script>

<div
	use:inview={{ rootMargin: inViewMargin, unobserveOnEnter: once }}
	on:inview_change={({ detail }) => {
		isInView = detail.inView ? 'visible' : 'hidden';
	}}
	class={cn('inline-block  text-black dark:text-white tracking-normal', className)}
	{...$$restProps}
>
	{$num.toFixed(0)}
</div>
