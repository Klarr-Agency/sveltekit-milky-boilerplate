<header class="header">
    <a href="/">
        <img class="header__logo"  src="/Klarr_Logo.svg" alt="klarr logo">
    </a>
    <nav class="navHeader">
        <ul class="navHeader__list">
            <li class="navHeader__item"><a class="navHeader__link" href="/admin/login">Login</a></li>
            <li class="navHeader__item"><a class="navHeader__link" href="/admin/register">Register</a></li>
        </ul>
    </nav>
</header>
<style lang="scss">
    .header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 24px;
        height: 50px;
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