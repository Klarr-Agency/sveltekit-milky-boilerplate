<script>
	export let checkboxValue;
</script>

<input class="checkbox" type="checkbox" bind:value={checkboxValue} />

<style lang="scss">
	.checkbox {
		appearance: none;
		-webkit-appearance: none;
		border: 2px solid #373854;
		border-radius: 4px;
		cursor: pointer;
		outline: none;
		transition: all 0.25s ease-out;
		margin: 0;
		height: 20px;
		width: 20px;
		&:hover,
		&:focus-visible {
			border-color: var(--color-primary);
		}
		&:checked {
			background-color: var(--color-primary);
			border-color: var(--color-primary);
			background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24' fill='none' stroke='%23fff' stroke-width='2' stroke-linecap='round' stroke-linejoin='round' class='feather feather-check'%3E%3Cpolyline points='20 6 9 17 4 12'%3E%3C/polyline%3E%3C/svg%3E");
			background-position: center;
			background-size: 100%;
		}
	}
</style>
