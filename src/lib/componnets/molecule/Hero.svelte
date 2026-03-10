<script>
	import {Bar,DownloadBtn,Logo} from '$lib'
	import catalogue from '$lib/Art Catalogue Daphne Bleeker.pdf'
</script>

<section class="hero">
	<Bar>
		<p>Daphne Bleeker catalogue</p>
		<p>2018 - now</p>
	</Bar>

	<Logo/>

	<Bar>
		<p class="download-bar-text">Get a copy </p>
		<DownloadBtn content={catalogue} onClick={() => {}}/>  
	</Bar>

</section>

<style>

	.hero{
		display: flex;
		flex-direction: column;
		height: fit-content;
		width: 100%;
		min-width: 300px;
		max-width: fit-content;
		color: var(--color-text);
		container-type: inline-size;
	}

	p.download-bar-text{
		font-size: 1.2rem;
		line-height:1.3;
	}

	@media (height < 450px){
		.hero{
			max-width:60%;
		}
	}

	
</style>