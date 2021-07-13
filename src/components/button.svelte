<script>
    export let text = "Button text";
    import { createEventDispatcher } from 'svelte';

	const dispatch = createEventDispatcher();

	function onButtonClick() {
		dispatch('click')
	}
</script>
<button class="button" on:click="{onButtonClick}">{text}</button>
<style lang="scss">
.button {
    background-color:#548c8b;
    border-radius: 12px;
    border: 0;
    color: #fff;
    font-family: 'Work Sans', sans-serif;
    font-weight: 400;
    font-size: 18px;
    padding: 12px 24px;
    cursor: pointer;
}
</style>