<script lang="ts">
	import favicon from '$lib/assets/D-logo.png';
	import Footer from '$lib/componnets/molecule/Footer.svelte';
	// import '../../static/app.css';



	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<main>
	{@render children?.()}
</main>
<Footer/>

<style>
	:global(html){
		background-color:var(--color-bg);
	}

	:global(body){
		display: flex;
		flex-direction: column;
		height: 100dvh;
	}

	main{
		flex: 1 0 auto;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: end;
		padding-bottom: 15dvh;
	}

	@media (height < 450px){
		main{
			padding-bottom: 4dvh;
		}
	}
</style>

