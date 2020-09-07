<template>
    <div>
        <div class="viodev-nav">
            <b-navbar toggleable="lg" type="dark" variant="dark">
                <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

                <b-collapse id="nav-collapse" is-nav>
                    <b-navbar-nav>
                        <b-nav-item>
                            <i class="material-icons">dehaze</i>
                        </b-nav-item>
                    </b-navbar-nav>

                    <b-navbar-nav class="mx-auto">
                        <b-navbar-brand
                            style="font-family: 'Source Code Pro', monospace !important;"
                            >VIOLET COMMUNITY ROMS</b-navbar-brand
                        >
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

.navbar.navbar-dark.bg-dark {
    opacity: 0.55;
}
</style>
