<div class="search">
	<input class="search__input" type="search" placeholder="Search" />
</div>

<style lang="scss">
	.search {
		&__input {
			background-color: var(--color-level-3);
			border-radius: 12px;
			border: 1px solid var(--color-border-input);
			color: #fff;
			font-family: var(--font-family);
			padding: 4px 16px;
			height: 43px;
			&:focus {
				outline: 0;
				border: 1px solid var(--color-secondary);
			}
		}
	}
</style>
