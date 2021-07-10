<script>
    import Link from "../components/link.svelte";
    let navLinks = [
        {url: "/admin/dashboard", text: "Dashboard",cssClass: "sideNav"},
        {url: "/admin/product", text: "Product", cssClass: "sideNav"},
        {url: "/admin/blogpost", text: "Blog Post", cssClass: "sideNav"}
    ];
</script>
<aside class="sideNav">
    <nav>
        <ul>
            {#each navLinks as {url,text, cssClass} }
            <li>
                <Link url={url} text={text} cssClass={cssClass}/>
            </li>
            {/each}
        </ul>
    </nav>
</aside>
<style lang="scss">
    .sideNav {
        grid-area: sideNav;
    }
</style>