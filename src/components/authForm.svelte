<script lang="typescript">
	import { goto } from '$app/navigation';
	import InputText from './inputText.svelte';
	import Button from '../components/button.svelte';
	import Link from '../components/link.svelte';
	type auth = 'login' | 'register';
	export let authType: auth;

	let loginInputs = [
		{ label: 'Username', type: 'text' },
		{ label: 'Password', type: 'password' }
	];
	let registerInputs = [
		{ label: 'Email', type: 'email' },
		{ label: 'Username', type: 'text' },
		{ label: 'Password', type: 'password' }
	];
	let loginPage = { url: '/auth/login', text: 'Sign in', cssClass: '' };
	let registerPage = { url: '/auth/register', text: 'Sign up', cssClass: '' };
	let loginButton = 'Log in';
	let registerButton = 'Register';

	function goToDashboard() {
		goto('/admin/dashboard');
	}
</script>

<section class="auth">
	<a href="/">
		<img class="auth__logo" src="/milky-logo-wt.svg" alt="klarr logo" />
	</a>
	<form class="auth__form">
		{#if authType === 'login'}
			{#each loginInputs as { label, type }}
				<InputText {label} />
			{/each}
			<div class="auth__buttons">
				<Button text={loginButton} on:click={goToDashboard} />
				<Link {...registerPage} />
			</div>
		{:else if authType === 'register'}
			{#each registerInputs as { label, type }}
				<InputText {label} />
			{/each}
			<div class="auth__buttons">
				<Button text={registerButton} on:click={goToDashboard} />
				<Link {...loginPage} />
			</div>
		{/if}
	</form>
</section>

<style lang="scss">
	.auth {
		display: flex;
		flex-direction: column;
		align-items: center;
		background-color: var(--color-level-2);
		border-radius: 32px;
		padding: 46px;
		min-height: 500px;
		width: 30%;
		&__logo {
			width: 200px;
		}
		&__form {
			display: flex;
			flex-direction: column;
			align-items: center;
			justify-content: center;
			flex: 1;
			width: 100%;
		}
		&__buttons {
			display: flex;
			align-items: center;
		}
	}
</style>
