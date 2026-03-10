<script>
	import {Bar,DownloadBtn,Logo} from '$lib'
	import catalogue from '$lib/Art Catalogue Daphne Bleeker.pdf'
	import {fade,fly} from 'svelte/transition'
	import {onMount} from 'svelte'

</script>

<section class="hero" >
	<Bar>
		<p>Daphne Bleeker catalogue</p>
		<p>2018 - Now</p>
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
		animation: fadeInUp 1s ease forwards;
	}

	p{
		display:block;
		opacity:0;
		animation: fadeInUp 1s ease .5s forwards;
	}

	p.download-bar-text{
		font-size: 1.2rem;
		line-height:1.3;
	}

	@keyframes fadeInUp {
		0% {
			opacity: 0;
			transform: translateY(20px);
		}
		100% {
			opacity: 1;
			transform: translateY(0);
		}
	}

	@media (height < 450px){
		.hero{
			max-width:60%;
		}
	}
</style>