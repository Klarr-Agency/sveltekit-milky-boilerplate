<script lang="typescript">
    type header = "frontend" | "backend";
    export let headerType:header;
</script>
<header class="header header--{headerType}">
    {#if headerType === "frontend"}
        <a href="/">
            <img class="header__logo"  src="/Klarr_Logo.svg" alt="klarr logo">
        </a>
        <nav class="navHeader">
            <ul class="navHeader__list">
                <li class="navHeader__item"><a class="navHeader__link" href="/auth/login">Login</a></li>
                <li class="navHeader__item"><a class="navHeader__link" href="/auth/register">Register</a></li>
            </ul>
        </nav>
    {:else if headerType === "backend"}
        <div class="logo">
            <img src="/klarr_logo.svg" alt="Backend logo" width="150px">
        </div>
        <div class="profil">
            <img class="profil__img" src="" alt="profil">
            <p class="profil__name">John Doe</p>
        </div>
    {/if}
</header>
<style lang="scss">
    .header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 24px;
        height: 50px;
        &--backend {
            display: flex;
            grid-area: header;
            justify-content: space-between;
            align-items: center;
        }
        &__logo {
            width: 150px;
        }
        .navHeader {
            &__list {
                display: flex;
                list-style-type: none;
                padding: 0;
                margin: 0;
            }
            &__item {
                margin: 0 12px;
            }
            &__link {
                color: #fff;
                text-decoration: none;
                font-family: 'Work Sans', sans-serif;
                font-weight: 400;
            }
        }
    }
</style>