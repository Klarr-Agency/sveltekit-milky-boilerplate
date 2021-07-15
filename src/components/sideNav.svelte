<script>
	import Link from '../components/link.svelte';
	import Icon from '../components/icon.svelte';
	let navLinks = [
		{ url: '/admin/dashboard', text: 'Dashboard', cssClass: 'link--sideNav', iconName: 'home' },
		{ url: '/admin/product', text: 'Product', cssClass: 'link--sideNav', iconName: 'products' },
		{ url: '/admin/blogpost', text: 'Blog Post', cssClass: 'link--sideNav', iconName: 'blog' }
	];
</script>

<aside class="sideNav">
	<nav>
		<ul class="sideNav__list">
			{#each navLinks as { url, text, cssClass, iconName }}
				<li class="sideNav__item">
					<Icon {iconName} />
					<Link {url} {text} {cssClass} />
				</li>
			{/each}
		</ul>
	</nav>
</aside>

<style lang="scss">
	.sideNav {
		background-color: var(--color-level-2);
		border-radius: 32px;
		margin: 0 24px 24px;
		grid-area: sideNav;
		$self: &;
		&__list {
			display: flex;
			flex-direction: column;
			justify-content: center;
			align-items: center;
			list-style-type: none;
			padding: 0;
			#{ $self }__item {
				display: flex;
				align-items: center;
				padding: 12px;
				font-size: 18px;
			}
		}
	}
</style>
