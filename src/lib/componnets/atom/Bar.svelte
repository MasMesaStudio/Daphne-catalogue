<script lang="ts">
	import type { Snippet } from 'svelte';
	let { children }: { children: Snippet } = $props();
</script>

<div class="bar">
	{@render children?.()}
</div>

<style>
	.bar{
		display: flex;
		flex-direction: row;
		justify-content:space-between;
		width: 100%;
		min-height: fit-content;
		padding-block: 10px;
	}

	.bar > :global(:is(a,button):nth-child(1):nth-last-of-type(1)){
		width: 100%;
		max-width: 100%;
		font-size: 1.25rem;
	}

	@media (max-width: 450px){
		.bar{
			flex-direction: column;
			gap: 10px;
		}
		
		.bar:nth-of-type(1){
			order: 2;
			padding-block: 1cqi;
		}
	}
	@media (max-width: 400px){

		.bar:nth-of-type(2){
			order: 0;
			font-size: max(1rem,100%);
			max-width: 100%;
		}
		.bar:nth-of-type(3){
			order: 1;
		}
	}
</style>