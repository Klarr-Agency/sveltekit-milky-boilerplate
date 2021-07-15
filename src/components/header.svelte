<script lang="typescript">
    import InputSearch from "../components/inputSearch.svelte";
    type header = "frontend" | "backend";
    export let headerType:header;
</script>
<header class="header header--{headerType}">
    {#if headerType === "frontend"}
        <a href="/">
            <img class="header__logo"  src="/milky-logo-wt.svg" alt="klarr logo">
        </a>
        <nav class="navHeader">
            <ul class="navHeader__list">
                <li class="navHeader__item"><a class="navHeader__link" href="/auth/login">Login</a></li>
                <li class="navHeader__item"><a class="navHeader__link" href="/auth/register">Register</a></li>
            </ul>
        </nav>
    {:else if headerType === "backend"}
        <div class="logoContainer">
            <a href="/admin/dashboard">
                <img class="header__logo" src="/milky-logo-wt.svg" alt="Backend logo">
            </a>
        </div>
        <div class="profile">
            <InputSearch/>
            <div class="profile__menu">
                <img class="profile__img" src="" alt="profil">
                <p class="profile__name">John Doe</p>
            </div>
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
        $self: &;
        &--backend {
            display: grid;
            grid-template-columns: 0.5fr 1fr 1fr;
            grid-template-areas: "logo title profile";
            grid-template-rows: 100px;
            grid-area: header;
            padding: 0;
            height: 100%;
            #{ $self }__logo {
                width: 130px;
            }
        }
        .logoContainer {
            display: flex;
            align-items: center;
            justify-content: center;
            grid-area: logo;
            height: 100%;
        }
        &__logo {
            width: 150px;
        }
        .profile {
            display: flex;
            align-items: center;
            justify-content: space-between;
            margin-right: 24px;;
            grid-area: profile;
            height: 100%;
            &__menu {
                display: flex;
                align-items: center;
            }
            &__img {
                border-radius: 100%;
                height: 30px;
                width: 30px;
            }
            &__name {
                color: #fff;
                font-family: var(--font-family);
                margin-left: 24px;
            }
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
                font-family: var(--font-family);
                font-weight: 400;
            }
        }
    }
</style>