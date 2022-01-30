<script>
	import { getStores } from '$app/stores';
	const { page } = getStores();
	export let url;
	export let text = 'Text for your link';
	export let cssClass;
	export let highlight;
	let highlightPath = false;
	$: highlightPath =
		$page.path && highlight && ($page.path.includes(highlight) || $page.path.includes(url));
</script>

<a class="link {cssClass}" class:selected={highlightPath} href={url}><slot />{text}</a>

<style lang="scss">
	.link {
		font-family: var(--font-family);
		font-weight: 400;
		text-decoration: none;
		padding: 12px 24px;
		color: #fff;
		&--sideNav {
			display: flex;
			align-items: center;
			color: #b2b3bd;
			padding: 12px;
			font-size: 16px;
			border-radius: 8px;
			width: 100%;
			&.selected {
				background-color: var(--color-primary);
				color: #fff;
				:global(svg) {
					stroke: #fff !important;
				}
				&:hover {
					color: #fff;
					:global(svg) {
						stroke: #fff !important;
					}
				}
			}
		}
		&:hover {
			color: var(--color-primary);
			:global(svg) {
				stroke: var(--color-primary) !important;
			}
		}
	}
</style>
