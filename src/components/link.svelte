<script>
	export let url;
	export let text = 'Text for your link';
	export let cssClass;
</script>

<a class="link {cssClass}" href={url}>{text}</a>

<style lang="scss">
	.link {
		font-family: var(--font-family);
		font-weight: 400;
		text-decoration: none;
		padding: 12px 24px;
		color: #fff;
		&:hover {
			color: var(--color-secondary);
		}
	}
</style>
