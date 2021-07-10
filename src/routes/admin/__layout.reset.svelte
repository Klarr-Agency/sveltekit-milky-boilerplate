<script>
    import Header from "../../components/header.svelte";
</script>
<div class="adminLayout">
    <Header headerType={"backend"}/>
    <aside class="sideNav">
        <nav>
            <ul>
                <li><a href="/admin/dashboard">Dashboard</a></li>
                <li><a href="/admin/product">Product</a></li>
                <li><a href="/admin/blogpost">Blog Post</a></li>
            </ul>
        </nav>
    </aside>
    <main class="mainContent">
        <slot></slot>
    </main>
</div>
<style lang="scss">
    .adminLayout {
        display: grid;
        grid-template-columns: 0.5fr 1fr 1fr;
        grid-template-rows: 80px 1fr;
        grid-template-areas: 
        "header header header"
        "sideNav main main";
        min-height: 100vh;
    }
    .sideNav {
        grid-area: sideNav;
    }
    .mainContent {
        grid-area: main;
    }
</style>