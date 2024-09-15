<script>
	import AnimatedGradientText from '$lib/components/AnimatedGradientText.svelte';
	import BiDirectionalBeam from '$lib/components/BiDirectionalBeam.svelte';
	import FlickeringGrid from '$lib/components/FlickeringGrid.svelte';
	import { cn } from '$lib/utils';
	import Marquee from '$lib/components/Marquee.svelte';
	import ReviewCard from '$lib/components/ReviewCard.svelte';
	import BlurFade from '$lib/components/BlurFade.svelte';
	import GradualSpacing from '$lib/components/GradualSpacing.svelte';
	import CirclesCard from '$lib/components/CirclesCard.svelte';
	import Globe from '$lib/components/Globe.svelte';
	import LetterPullUp from '$lib/components/LetterPullUp.svelte';
	import RetroGrid from '$lib/components/RetroGrid.svelte';
	import GridPattern from '$lib/components/GridPattern.svelte';
	import ShineBorder from '$lib/components/ShineBorder.svelte';
	import MagicCard from '$lib/components/MagicCard.svelte';

	const reviews = [
		{
			name: 'Bhide',
			username: '@Bhide',
			body: 'Noicee work. I love it. Keep it up.',
			img: 'https://avatar.vercel.sh/jack'
		},
		{
			name: 'Jodd',
			username: '@Jodd',
			body: 'Wooww, this is what I was looking for. Great work.',
			img: 'https://avatar.vercel.sh/jill'
		},
		{
			name: 'Pokie',
			username: '@Pokie',
			body: 'Svelte is Amazing and so are you. Keep it up.',
			img: 'https://avatar.vercel.sh/john'
		},
		{
			name: 'pablo',
			username: '@pablo',
			body: 'Remarkable Stuff broooo. Added to my favourites.',
			img: 'https://avatar.vercel.sh/jane'
		},
		{
			name: 'Saloni',
			username: '@Saloni',
			body: 'Acche hai, Chal mera Portfolio banade.',
			img: 'https://avatar.vercel.sh/jenny'
		},
		{
			name: 'Bhai',
			username: '@Bhai',
			body: 'Svelte made easy with these components. Great work.',
			img: 'https://avatar.vercel.sh/james'
		}
	];

	let firstRow = reviews.slice(0, reviews.length / 2);
	let secondRow = reviews.slice(reviews.length / 2);
</script>

<div
	class="relative rounded-lg w-full mx-auto bg-background overflow-hidden flex items-center justify-center h-screen"
>
	<FlickeringGrid
		class="z-0 absolute inset-0 size-full"
		squareSize={4}
		gridGap={6}
		color="#6B7280"
		maxOpacity={0.5}
		flickerChance={0.1}
		width={1920}
		height={1080}
	/>

	<div>
		<div class="z-10 flex items-center justify-center flex-col gap-6">
			<GradualSpacing
				class="font-geist text-center text-2xl font-bold tracking-[-0.1em]  text-black dark:text-white md:text-7xl md:leading-[5rem] text-wrap"
				words="How Wild Can I Make This?"
			/>
			<a href="https://animation-svelte.vercel.app/" target="_blank">
				<AnimatedGradientText>
					🔥 <hr class="mx-2 h-4 w-[1px] shrink-0 bg-gray-300" />
					{' '}
					<span
						class={cn(
							`inline animate-gradient bg-gradient-to-r from-[#ffaa40] via-[#9c40ff] to-[#ffaa40] bg-[length:var(--bg-size)_100%] bg-clip-text text-transparent`
						)}
					>
						Checkout This Library
					</span>
					<svg
						xmlns="http://www.w3.org/2000/svg"
						width="24"
						height="24"
						viewBox="0 0 24 24"
						fill="none"
						stroke="currentColor"
						stroke-width="2"
						stroke-linecap="round"
						stroke-linejoin="round"
						class="ml-1 size-3 transition-transform duration-300 ease-in-out group-hover:translate-x-0.5"
						><path d="m9 18 6-6-6-6" /></svg
					>
				</AnimatedGradientText>
			</a>
		</div>
	</div>
</div>

<section id="header" class="font-geist pt-8 pl-8">
	<BlurFade delay={0.25}>
		<h2 class="text-3xl font-bold tracking-tighter sm:text-5xl xl:text-6xl/none">Reviews</h2>
	</BlurFade>
	<BlurFade delay={0.25 * 2}>
		<span class="text-xl text-pretty tracking-tighter sm:text-3xl xl:text-4xl/none">
			Wow these are all so real thats crazy
		</span>
	</BlurFade>
</section>

<div
	class="relative flex h-full w-full flex-col items-center justify-center overflow-hidden rounded-lg bg-background py-20 md:shadow-xl"
>
	<Marquee pauseOnHover class="[--duration:20s]">
		{#each firstRow as item}
			<ReviewCard {...item} />
		{/each}
	</Marquee>
	<Marquee reverse pauseOnHover class="[--duration:20s]">
		{#each secondRow as item}
			<ReviewCard {...item} />
		{/each}
	</Marquee>
	<div
		class="pointer-events-none absolute inset-y-0 left-0 w-1/3 bg-gradient-to-r from-white dark:from-neutral-950"
	></div>
	<div
		class="pointer-events-none absolute inset-y-0 right-0 w-1/3 bg-gradient-to-l from-white dark:from-neutral-950"
	></div>
</div>

<LetterPullUp words="Easy ways to make stuff look good" class="text-wrap text-md md:text-3xl" />

<div class=" w-full flex md:flex-row flex-col items-center justify-center gap-4">
	<CirclesCard />

	<BiDirectionalBeam />

	<div class="flex justify-center items-center">
		<div
			class="relative flex h-fit w-full md:max-w-[32rem] max-w-[22rem] items-center justify-center overflow-hidden rounded-lg bg-background px-40 pb-40 pt-8 md:pb-60 md:shadow-xl"
		>
			<span
				class="pointer-events-none select-none whitespace-pre-wrap bg-gradient-to-b from-black to-gray-300/80 bg-clip-text text-center text-8xl font-semibold leading-none text-transparent dark:from-white dark:to-slate-900/10"
			>
				Earth
			</span>
			<Globe class="top-28" />
			<div
				class="pointer-events-none absolute inset-0 h-full bg-[radial-gradient(circle_at_50%_200%,rgba(0,0,0,0.2),rgba(255,255,255,0))]"
			></div>
		</div>
	</div>
</div>

<div
	class="relative flex size-full items-center justify-center overflow-hidden rounded-lg bg-background p-20 md:shadow-xl"
>
	<span
		class="pointer-events-none z-10 whitespace-pre-wrap bg-gradient-to-b from-[#d2e6d8] via-[#ab013c] to-[#1e4fff] bg-clip-text text-center text-7xl font-bold leading-none tracking-tighter text-transparent"
	>
		This is Sick
	</span>

	<RetroGrid />
</div>

<div
	class="relative flex h-fit w-full items-center justify-center overflow-hidden rounded-lg bg-background p-20 md:shadow-xl"
>
	<div class="flex justify-center items-center w-full min-h-52">
		<!-- Add Border colors in array of strings  -->
		<ShineBorder
			class="bg-neutral-950 text-center text-2xl font-bold capitalize"
			color={['#FF057A', '#0883FF']}
		>
			Svelte is Fun
		</ShineBorder>
	</div>
	<GridPattern
		width={30}
		height={30}
		strokeDashArray="4 2"
		class={cn('[mask-image:radial-gradient(700px_circle_at_center,white,transparent)]')}
	/>
</div>

<div class="flex w-full flex-col gap-4 h-[250px] lg:flex-row">
	<MagicCard
		class="cursor-pointer flex-col items-center justify-center shadow-2xl whitespace-nowrap text-4xl group hover:border-[#2effbd9e] transition-all duration-300"
		gradientColor="#043634"
		gradientSize={300}
	>
		<div
			class="group-hover:text-[#2EFFBD] transition-all duration-500 flex gap-1.5 justify-center items-center font-semibold"
		>
			<!-- <img src={SupabaseSvg} alt="svelte_logo" class="size-10 mt-1.5" /> -->
			Supabase
		</div>
	</MagicCard>
	<MagicCard
		class="cursor-pointer flex-col items-center justify-center shadow-2xl whitespace-nowrap text-4xl group hover:border-[#ff770094] transition-all duration-300"
		gradientColor="#4D2506"
	>
		<div
			class="group-hover:text-[#FF7700] transition-all duration-500 flex gap-1.5 justify-center items-center font-semibold"
		>
			<!-- <img src={SvelteSvg} alt="svelte_logo" class="size-10 mt-1.5" /> -->
			Svelte
		</div>
	</MagicCard>
	<MagicCard
		class="cursor-pointer flex-col items-center justify-center shadow-2xl whitespace-nowrap text-4xl group hover:border-[#07e351] transition-all duration-300"
		gradientColor="#07e351"
	>
		<div
			class="group-hover:text-[#07e351] transition-all duration-500 flex gap-1.5 justify-center items-center font-semibold"
		>
			<!-- <img src={SvelteSvg} alt="svelte_logo" class="size-10 mt-1.5" /> -->
			Insiderviz
		</div>
	</MagicCard>
</div>

<footer class="flex items-center justify-center py-8">
	<h2>
		Built by <a
			href="https://twitter.com/bmdavis419"
			target="_blank"
			class="font-bold hover:underline">Ben Davis</a
		>
		-
		<a
			href="https://github.com/bmdavis419/crazy-sveltekit-animations"
			target="_blank"
			class="font-bold hover:underline">GitHub</a
		>
	</h2>
</footer>
