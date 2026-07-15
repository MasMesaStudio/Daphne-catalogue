<script>
	import {Bar,CatOptionBtn,Logo} from '$lib'
	import catalogue from '$lib/catalouges-pdf/Art Catalogue Daphne Bleeker.pdf'
	let {
		title = 'Daphne Bleeker catalogue',
		traject = '2018 - Now',
		DText = 'Get a copy',
		Mimg,
		catalogueSrc = catalogue,
		children,
		extraContent
		// logoExtra
	} = $props()	

</script>

<section class="hero" >
	<Bar>
		<p>{title}</p>
		<p>{traject}</p>
		{#each extraContent as x (x.innerText) }
			<p class="innerText">{x.innerText}</p>
		{/each}
	</Bar>
	<Logo img="{Mimg}">
		{@render children?.()}
	</Logo>
	<Bar>
		<CatOptionBtn content={catalogueSrc} type="open" text="Open Catalogue" />  
	</Bar>
	<Bar>
		<p class="download-bar-text">{DText} </p>
		<CatOptionBtn content={catalogueSrc} type="link" />  
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

	p.innerText{
		display: none;
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

	@media (max-width: 450px){
		p.innerText{
			display: inline;
		}
	}
</style>