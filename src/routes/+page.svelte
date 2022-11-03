<script>
	let link = 'https://i-sedekah.id';

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
			title: 'Macbook Pro',
			width: 1280,
			height: 800
		}
	];

	let x, y;

	$: console.log(x, y);
</script>

<svelte:window bind:innerWidth={x} bind:innerHeight={y} />
<section >
    <h1 class="text-white">My Responsive dev</h1>
	<input type="text" bind:value={link} class="min-w-[400px] rounded-md py-3 px-8 m-2" />
	<div class="flex gap-1 relative  ">
		{#each screenMotive as screen}
			<div class="text-white w-full scale-[0.6] max-w-[300px] max-h-0 relative ">
				<p>{screen.title}</p>
				<iframe
					src={link}
					width={screen.width}
					height={screen.height}
					style={`border:1px solid black;`}
					title={screen.title}
                    class="-ml-10"
                    
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
