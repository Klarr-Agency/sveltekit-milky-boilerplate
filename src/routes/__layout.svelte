<script>
    import Header from "../components/header.svelte";
</script>
<div class="wrapper">
    <Header/>
    <slot></slot>
</div>
<style>
    .wrapper {
        background-color: #1B1B1B;
        min-height: 100vh;
    }
</style>
