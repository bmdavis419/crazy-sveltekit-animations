<script>
	import BiDirectionalBeam from '$lib/components/BiDirectionalBeam.svelte';
	import FlickeringGrid from '$lib/components/FlickeringGrid.svelte';
</script>

<div
	class="relative h-64 md:h-[600px] rounded-lg w-full mx-auto bg-background overflow-hidden flex items-center justify-center"
>
	<FlickeringGrid
		class="z-0 absolute inset-0 size-full"
		squareSize={4}
		gridGap={6}
		color="#6B7280"
		maxOpacity={0.5}
		flickerChance={0.1}
		width={1920}
		height={600}
	/>

	<h2 class="text-center text-5xl font-bold z-10">This is Fucking Sick</h2>
</div>

<BiDirectionalBeam />
