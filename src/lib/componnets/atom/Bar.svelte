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

	@media (max-width: 400px){
		.bar{
			flex-direction: column;
			gap: 10px;
		}

		.bar:nth-of-type(1){
			order: 2;
		}
		.bar:nth-of-type(2){
			order: 3;
		}
	}


</style>