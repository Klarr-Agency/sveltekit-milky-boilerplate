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
			url: '/admin/product',
			text: 'Product',
			cssClass: 'link--sideNav',
			iconName: 'products',
			highlight: 'product'
		},
		{
			url: '/admin/blogpost',
			text: 'Blog Post',
			cssClass: 'link--sideNav',
			iconName: 'blog',
			highlight: 'blog'
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
		border-radius: 32px;
		margin: 24px;
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
			}
		}
	}
</style>
