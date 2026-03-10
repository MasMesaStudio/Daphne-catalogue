<script lang="ts">
	let {type = 'link',content, text = 'Download', onClick}: {type?: string, text?: string,content:string, onClick: () => void} = $props();
</script>


{#if type === 'button'}
	<button onclick={onClick} title="Download {type}">
	{text}
	</button>
{:else if type === 'link'}
	<a href={content} download title="Download {type}">
		<svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
			<path d="M8 12L3 7L4.4 5.55L7 8.15V0H9V8.15L11.6 5.55L13 7L8 12ZM2 16C1.45 16 0.979167 15.8042 0.5875 15.4125C0.195833 15.0208 0 14.55 0 14V11H2V14H14V11H16V14C16 14.55 15.8042 15.0208 15.4125 15.4125C15.0208 15.8042 14.55 16 14 16H2Z" />
		</svg>
	</a>
{/if}

<style>
	:is(a,button){
		--_btn-color-bg: var(--color-text);
		--_btn-text-color:var(--color-btn);
		display: grid;
		place-content:center;
		padding: 3% 8%;
		width: 40%;
		max-width: 150px;
		max-height: 3rem;
		background: var(--_btn-color-bg);
		color: var(--_btn-text-color);
		border: none ;
		font-size: 1rem;
		transition: background-color .3s ease;	
		cursor: pointer;

		svg{
			fill: var(--_btn-text-color);
			transition: fill .3s ease;
		}
	}

	:is(a,button):hover{
		background: var(--color-bg);
		outline: solid var(--_btn-color-bg) 2px ;
		color: var(--_btn-color);

		svg{fill: var(--_btn-color-bg);}
	}

	:is(a,button):is(:active,:focus-visible){
		background: yellow;
		color: var(--btn-color);
		svg{fill: var(--btn-color);}
	}
</style>