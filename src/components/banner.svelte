<script>
	import Button from '../components/button.svelte';
	export let title = 'Default';
	export let description = 'This is the default description for this page';
	export let buttonLabel = 'New button';
	export let button = false;
</script>

<div class="banner">
	<div class="banner__detail">
		<h1 class="banner__title">{title}</h1>
		<p class="banner__description">{description}</p>
	</div>
	{#if button === true}
		<Button text={buttonLabel} />
	{/if}
</div>

<style lang="scss">
	.banner {
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 64px 32px;
		&__title {
			font-family: var(--font-family);
			text-transform: capitalize;
			font-size: 56px;
			font-weight: 700;
			color: #fff;
			margin: 0;
		}
		&__description {
			font-family: var(--font-family);
			font-weight: 300;
			margin: 0;
			color: #b2b3bd;
		}
	}
</style>
