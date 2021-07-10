<script>
    import AuthForm from "../../components/authForm.svelte";
</script>
<div class="register">
    <AuthForm authType={"register"}/>
</div>
<style lang="scss">
    .register {
        display: grid;
        place-items: center;
        height: 100vh;
    }
</style>
