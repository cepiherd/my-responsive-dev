<script>
	let link = '';

	let screenMotive = [
		{
			title: 'Iphone 14',
			width: 428,
			height: 928
		},
		{
			title: 'Samsung',
			width: 360,
			height: 800
		},
		{
			title: 'Ipad Mini',
			width: 768,
			height: 1024
		},
		{
			title: 'Macbook Air',
			width: 1280,
			height: 800
		}
	];

	let x, y;

	$: console.log(x, y);
</script>

<svelte:window bind:innerWidth={x} bind:innerHeight={y} />
<section>
    <h1 class="font-extrabold text-white text-center py-10 text-2xl">Enjoy localhost develop</h1>
	<input
		type="text"
		bind:value={link}
        placeholder="Your url"
		class="min-w-[400px] rounded-md py-3 px-8 m-2 bg-white/10 shadow-lg text-white"
	/>
	<div class={`flex gap-4 relative scale-[.6] absolute -mt-[10em] -ml-[22rem]`}>
		{#each screenMotive as screen}
			<div
				class={`text-white  relative `}
				style={`max-width:${screen.width}; max-height:${screen.height}`}
			>
				<p class="bg-red-400 rounded text-center py-3">{screen.title}</p>
				<p>{screen.width} x {screen.height}</p>
				<iframe
					sandbox="allow-top-navigation allow-scripts allow-forms"
					src={link}
					width={screen.width}
					height={screen.height}
					style={`border:1px solid black;`}
					title={screen.title}
					class=" bg-white  rounded-lg"
				/>
			</div>
		{/each}
	</div>
</section>

<style>
	.flex {
		display: flex;
	}

	.relative {
		position: relative;
	}

	:root {
		background-color: #14213d;
	}
</style>
