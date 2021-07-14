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
        <ul class="sideNav__list">
            {#each navLinks as {url,text, cssClass} }
            <li class="sideNav__item">
                <Link url={url} text={text} cssClass={cssClass}/>
            </li>
            {/each}
        </ul>
    </nav>
</aside>
<style lang="scss">
    .sideNav {
        background-color: var(--color-level-2);
        border-radius: 32px;
        margin: 0 24px 24px;
        grid-area: sideNav;
        $self: &;
        &__list {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            list-style-type: none;
            padding: 0;
            #{ $self }__item {
                padding: 12px;
                font-size: 18px;
            }
        }
    }
</style>