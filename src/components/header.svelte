<script lang="typescript">
	import InputSearch from '../components/inputSearch.svelte';
	type header = 'frontend' | 'backend';
	export let headerType: header;
</script>

<header class="header header--{headerType}">
	{#if headerType === 'frontend'}
		<a href="/">
			<img class="header__logo" src="/milky-logo-wt.svg" alt="klarr logo" />
		</a>
		<nav class="navHeader">
			<ul class="navHeader__list">
				<li class="navHeader__item">
					<a class="navHeader__link" href="/auth/login">Login</a>
				</li>
				<li class="navHeader__item">
					<a class="navHeader__link" href="/auth/register">Register</a>
				</li>
			</ul>
		</nav>
	{:else if headerType === 'backend'}
		<div class="profile">
			<InputSearch />
			<div class="profile__menu">
				<div class="profile__imgWrapper">
					<img class="profile__img" src="../elise-wilcox.jpg" alt="profil" />
				</div>
				<p class="profile__name">Elise Wilcox</p>
			</div>
		</div>
	{/if}
</header>

<style lang="scss">
	.header {
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 24px;
		height: 50px;
		$self: &;
		&--backend {
			display: grid;
			grid-template-columns: 0.5fr 1fr 1fr;
			grid-template-areas: 'logo title profile';
			grid-template-rows: 100px;
			grid-area: header;
			padding: 0;
			margin: 0 64px;
			height: 100%;
			#{ $self }__logo {
				width: 130px;
			}
		}
		.profile {
			display: flex;
			align-items: center;
			justify-content: space-between;
			grid-area: profile;
			height: 100%;
			&__menu {
				display: flex;
				align-items: center;
			}
			&__imgWrapper {
				position: relative;
				border-radius: 100%;
				overflow: hidden;
				height: 40px;
				width: 40px;
			}
			&__img {
				position: absolute;
				width: 100%;
			}
			&__name {
				color: #fff;
				font-family: var(--font-family);
				margin-left: 16px;
			}
		}
		.navHeader {
			&__list {
				display: flex;
				list-style-type: none;
				padding: 0;
				margin: 0;
			}
			&__item {
				margin: 0 12px;
			}
			&__link {
				color: #fff;
				text-decoration: none;
				font-family: var(--font-family);
				font-weight: 400;
			}
		}
	}
</style>
