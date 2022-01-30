<script>
	export let label = 'label';
	export let placeholder = '';
	export let inputValue = '';
</script>

<div class="inputText">
	<label for={label} class="inputText__label">{label}</label>
	<input id={label} type="text" class="inputText__input" {placeholder} bind:value={inputValue} />
</div>

<style lang="scss">
	.inputText {
		display: flex;
		flex-direction: column;
		margin-bottom: 24px;
		width: 100%;
		&__label {
			color: #fcfcfc;
			font-size: 18px;
			font-family: 'Work Sans', sans-serif;
			font-weight: 400;
			margin-bottom: 8px;
		}
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
