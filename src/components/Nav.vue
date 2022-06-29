<template>
    <div class="wrapper">
        <nav>
            <ul>
                <li>
                    <RouterLink to="/">Home</RouterLink>
                </li>

                <li>
                    <RouterLink to="/about">About</RouterLink>
                </li>
            </ul>
        </nav>
    </div>
</template>

<style lang="scss">
nav {
    background-color: #346;
    padding-block: 1.5rem;
    padding-inline-end: 1.5rem;

    ul {
        display: flex;
        justify-content: flex-end;
        gap: 3em;
        list-style-type: none;

        a {
            color: #fff;
            text-decoration: none;

            &:visited {
                color: #fff;

            }

            &:hover {
                color: coral;
            }

            &.router-link-active {
                text-decoration: underline;
            }
        }
    }
}
</style>
