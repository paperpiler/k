<template>
    <div>
        <Navbar />
        <div>
            <SearchBar />
        </div>
    </div>
</template>

<script>
import Navbar from "./components/Navbar";
import SearchBar from "./components/SearchBar";

export default {
    name: "App",
    components: {
        Navbar,
        SearchBar,
    },
};
</script>

<style>
@import "https://fonts.googleapis.com/css2?family=Source+Code+Pro:wght@600&display=swap";

body {
    background-color: #212121 !important;
}
</style>
