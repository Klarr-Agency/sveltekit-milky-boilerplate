<script>
	import Grid from '../../components/grid.svelte';
	import Banner from '../../components/banner.svelte';
</script>

<svelte:head>
	<title>Dashboard - Recipes</title>
</svelte:head>
<Banner title="Recipes" buttonLabel="New recipe" button={true} />
<section class="page__content">
	<Grid />
</section>

<style lang="scss">
	.page {
		&__content {
			display: block;
			position: relative;
			padding: 32px 50px 32px 40px;
			border-radius: 24px;
			background: var(--color-level-2);
		}
	}
</style>
