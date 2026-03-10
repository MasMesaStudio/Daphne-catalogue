<h1>
	<a href="/">
		<img width=100 height=200 src="/687406890100dcdbb2d5d3a2_DaphneBleeker logo2.png" alt="Daphne Bleeker Logo">
	</a>
</h1>

<style>
	h1 {
		flex:1 0 auto;
		position: relative;
		display: block;
		width: 100%;
		margin-block: .5rem;
		padding: 0;
		pointer-events: none;
	}

	a{
		position: relative;
		display: grid;
		width: 100%;
		padding-block: 2rem;
		height: fit-content;
		place-content: center;
		border:solid var(--color-text) 2px;
	}

	img{
		min-width: 250px;
		width: 100%;
		height: auto;
		object-fit: cover;
		object-position: center;
	}

	@media (prefers-color-scheme: dark) {
		a{
			border:unset;
			color: var(--color-text);
			border-block: solid currentcolor 2px;
		}
		
		img{filter: invert(1);}
	}

	@media (max-width: 400px){
		a{
			border:unset;
			color: var(--color-text);
			border-bottom: solid currentcolor 2px;
		}
	}

	@media (height < 450px){
		a{
			border:unset;
			border-bottom: solid currentcolor 2px;
			align-self: start;
			justify-content:start;
		}
		img{
			min-width: 10dvw ;
			width:14dvw;
		}
	}

</style>