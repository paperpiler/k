<template>
    <center>
        <div id="SearchBar">
        <input
            type="text"
            style="font-family: Source Code Pro"
            placeholder="Search..."
            class="rsearch"
        />
    </div>
    </center>
</template>

<script>
export default {
    name: "SearchBar",
};
</script>

<style scoped>
.rsearch {
    border-radius: 10px;
    width: 550px;
    height: 50px;
    margin-top: 150px;
    border: 0vw;
    text-indent: 10px;
}
</style>
