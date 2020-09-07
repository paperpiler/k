<template>
    <div>
        <div>
            <b-navbar toggleable="lg" type="dark" variant="dark">
                <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

                <b-collapse id="nav-collapse" is-nav>
                    <b-navbar-nav>
                        <b-nav-item>
                            <i class="material-icons">dehaze</i>
                        </b-nav-item>
                    </b-navbar-nav>

                    <b-navbar-nav class="mx-auto">
                        <b-navbar-brand>VioDev</b-navbar-brand>
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

<style>
@import "https://fonts.googleapis.com/icon?family=Material+Icons";
</style>
