<script>
	import Header from '../../components/header.svelte';
	import SideNav from '../../components/sideNav.svelte';
</script>

<svelte:head>
	<title>Dashboard</title>
</svelte:head>
<div class="adminLayout">
	<SideNav />
	<Header headerType={'backend'} />
	<main class="mainContent">
		<slot />
	</main>
</div>

<style lang="scss">
	.adminLayout {
		display: grid;
		grid-template-columns: 0.5fr 1fr 1fr;
		grid-template-rows: auto 1fr;
		grid-template-areas:
			'sideNav header header'
			'sideNav main main';
		min-height: 100vh;
	}
	.mainContent {
		grid-area: main;
		margin: 24px;
	}
</style>
