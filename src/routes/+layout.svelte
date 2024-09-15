<script>
	import '../app.css';

	const { children } = $props();
</script>

<div class="bg-neutral-950 text-white min-h-screen">
	{@render children()}
</div>
