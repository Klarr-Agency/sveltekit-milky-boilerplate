<script>
	import SideNavLink from '../components/sideNavlink.svelte';
	import Icon from '../components/icon.svelte';

	let navLinks = [
		{
			url: '/admin/dashboard',
			text: 'Dashboard',
			cssClass: 'link--sideNav',
			iconName: 'home',
			highlight: 'dashboard'
		},
		{
			url: '/admin/recipes',
			text: 'Recipes',
			cssClass: 'link--sideNav',
			iconName: 'pie',
			highlight: 'recipes'
		},
		{
			url: '/admin/posts',
			text: 'Posts',
			cssClass: 'link--sideNav',
			iconName: 'blog',
			highlight: 'posts'
		}
	];
</script>

<aside class="sideNav">
	<div class="logoContainer">
		<a href="/admin/dashboard">
			<img class="sideNav__logo" src="/milky-logo-wt.svg" alt="Backend logo" />
		</a>
	</div>
	<nav>
		<ul class="sideNav__list">
			{#each navLinks as { url, text, cssClass, iconName, highlight }}
				<li class="sideNav__item">
					<SideNavLink {url} {text} {cssClass} {highlight}>
						<div class="sideNav__icon">
							<Icon {iconName} />
						</div>
					</SideNavLink>
				</li>
			{/each}
		</ul>
	</nav>
</aside>

<style lang="scss">
	.sideNav {
		background-color: var(--color-level-2);
		border-right: 1px solid var(--color-border-input);
		padding: 32px;
		grid-area: sideNav;
		$self: &;
		.logoContainer {
			display: flex;
			align-items: center;
			justify-content: center;
		}
		&__logo {
			width: 150px;
		}
		&__list {
			list-style-type: none;
			padding: 0;
			margin: 32px 0 0;
			#{ $self }__item {
				display: flex;
				align-items: center;
			}
			#{ $self }__icon {
				margin-right: 16px;
				:global(svg) {
					stroke: #b2b3bd;
				}
			}
		}
	}
</style>
