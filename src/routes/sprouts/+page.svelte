<script>
	import {Hero} from '$lib';
	import catalogue from '$lib/catalouges-pdf/foodware Catalogue Daphne Bleeker.pdf'

	let sproutInfos = [
		{src:'/sprouts/Catalogue-DaphneBleeker.png', alt:'artist',innerText:'Daphne Bleeker'},
		{src:'/sprouts/Catalogue-adres.png', alt:'adres',innerText:'Looiergracht 12, AMS'},
		{src:'/sprouts/Catalogue-exhibition.png', alt:'exhibition',innerText:''},
		{src:'/sprouts/Catalogue-Time.png', alt:'time',innerText:'Jul 19, 12:00-17:00'},
	]

	const sprouts = {
		title:'',
		traject:'',
		Dtext:null,
		Mimg:'./sprouts/squaretje.png',
		catalogueSrc:catalogue,
		extraContent:sproutInfos
	}

</script>

	<Hero {...sprouts} >
		<div class="info-container">
		<div class="info-inner-layer">
			{#each sproutInfos as info (info.src)}
				<img src={info.src} alt={info.alt} class={info.alt} width="50" height="50">
			{/each}
		</div>
		</div>

	</Hero>

<style>
	:root{
		--color-bg:#e1e325;
		--color-highlight:var(--black);
    	--color-highlight-text:#e1e325;
	}

	:global(.hero .logo-square a){
		border: none;
	}

	:global(.logo-square a img){
		scale: 1.05;
		filter: blur(0) grayscale(0) brightness(0.9) contrast(2);
		transition: filter 1s ease,scale 1s ease ;
		/* display: none; */
		
		
	}

	.info-container{
		position: absolute;
		inset-inline: -8cqw ;
		inset-block: 1dvh ;
		pointer-events: none;
	}

	/* info img sections */
	.info-inner-layer{
		position: relative;
		height: 100%;
		container-type: inline-size;
	}

	.info-inner-layer img{
		--scale:75%;
		position: absolute;
		filter: grayscale(0) brightness(0.6) contrast(2);
		transition: filter 2s ease, all 200ms ease;

		
		
		&.artist{
			height: fit-content;
			width: var(--scale);
			inset-inline: 15% ;
			top: 0;
			text-align: center;
		}
		&.exhibition{
			height: fit-content;
			width: 60%;
			inset-inline: 20% ;
			bottom: 0;
			text-align: center;
		}
		&.time{
			width: fit-content;
			height: 85%;
			right: 0;
			left: auto;
			inset-block: 8% 10%;
			max-width: 1rem;
		}
		&.adres{
			width: fit-content;
			max-width: 1rem;
			height: var(--scale,100%);
			height: 70%;
			left: 0;
			right: auto;
			inset-block:calc((100% - var(--scale)) / 2) ;
			top: 8%;
		}
	}

	:global(.hero:is(:hover,:focus-within)){
		
		:global(.logo-square a img){
			filter: blur(2.5px) grayscale(1) brightness(0.5);
			scale: 1.047;
			transition: filter 1s ease,scale 1s ease ;
		}

		.info-inner-layer img{
			filter: grayscale(2) contrast(2) brightness(0);

			&.artist{
				inset-inline: 15% ;
				/* top: 7cqh; */
				/* filter: blur(2px); */
			}
			&.exhibition{
				inset-inline: 20% ;
				/* bottom: 7cqh; */
				/* filter: blur(2px); */
			}
		}
	}

	@media(max-width:450px){
		:global(.logo-square a img){
			/* display: none; */
			outline: solid .1px rgba(129, 129, 129, 0.002) ;
			/* appearance: none; */

		}

		.info-inner-layer img{
			display: none ;
		}
	}

	@media(height < 450px){
		.info-inner-layer img{
			display: none;
		}
	}

	@media (prefers-color-scheme: dark) {
		:root {
			--color-bg:#959618;
			--color-bg:#49490b;
			--color-highlight:#e1e325;
    		--color-highlight-text:black;
		}

		:global(.hero .logo-square a img){
			filter: blur(0) grayscale(0) brightness(1.9) contrast(2) ;
			background-attachment: fixed;
			background-color: transparent;
			transition:filter 1s ease ;
		}
		
		.info-inner-layer img{
			filter: grayscale(0) brightness(1) contrast(0);
			transition: 500ms ease;
		}

		:global(.hero:is(:hover,:focus-within)){
		
			:global(.logo-square a img){
				filter: blur(2.3px) grayscale(0) brightness(1.6) contrast(2);
				transition: filter 1s ease ;
			}

			.info-inner-layer img{
				filter: grayscale(0) brightness(1) contrast(0);
				transition: 1s ease;
			}

			.info-inner-layer img:is(.time,.adres){
				filter: grayscale(0) brightness(2) contrast(1);
			}
		}
	 
	}
</style>