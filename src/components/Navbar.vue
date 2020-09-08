<template>
    <div class="viodev-nav">
        <div>
            <b-navbar toggleable="lg" type="dark" variant="dark">
                <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

                <b-collapse id="nav-collapse" is-nav>
                    <b-navbar-nav>
                        <b-nav-item>
                            <i class="material-icons">dehaze</i>
                        </b-nav-item>
                    </b-navbar-nav>

                    <b-navbar-nav>
                        <b-navbar-brand class="header-text">
                                FORMAT SWITCHER
                            </b-navbar-brand>
                    </b-navbar-nav>
                </b-collapse>
            </b-navbar>
        </div>
    </div>
</template>

<script>
export default {
    name: "Navbar",
};
</script>

<style scoped>
@import "https://fonts.googleapis.com/icon?family=Material+Icons";

.viodev-nav {
    width: 100vw;
}

.navbar.navbar-dark.bg-dark {
    opacity: 0.55;
}

.header-text {
    font-family: Source Code Pro;
    color: aliceblue !important;
}

</style>
