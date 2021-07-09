<section class="auth">
    <img class="auth__logo"  src="/Klarr_Logo.svg" alt="klarr logo">
    <InputField/>
    <Button/>
</section>
<style lang="scss">
    .auth {
        display: flex;
        flex-direction: column;
        align-items: center;
        background-color: #202020;
        border-radius: 32px;
        padding: 46px;
        min-height: 500px;
        width: 30%;
        &__logo {
            width: 200px;
        }
    }
</style>
<script>
    import InputField from "../components/inputField.svelte";
    import Button from "../components/button.svelte";
</script>