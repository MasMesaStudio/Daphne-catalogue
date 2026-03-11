<script>
	import {Bar,DownloadBtn,Logo} from '$lib'
	import catalogue from '$lib/Art Catalogue Daphne Bleeker.pdf'
	import {fade,fly} from 'svelte/transition'
	import {onMount} from 'svelte'
	const title = $state('Daphne Bleeker catalogue')
	const traject = $state('2018 - Now')
	const DText = $state('Get a copy')
</script>

<section class="hero" >
	<Bar>
		<p>{title}</p>
		<p>{traject}</p>
	</Bar>
	<Logo/>
	<Bar>
		<p cass="download-bar-text">{DText} </p>
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