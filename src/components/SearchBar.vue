<template>
    <div id="SearchBar">
        <b-nav-form class="">
            <b-form-input
                size="sm"
                class="mr-sm-2"
                placeholder="🔍 Search"
            ></b-form-input>
        </b-nav-form>

        <input
            type="text"
            style="text-align: center"
            placeholder="Search..."
            class="rsearch"
        />
    </div>
</template>

<script>
export default {
    name: "SearchBar",
};
</script>

<style scoped>
.rsearch {
    border-radius: 14px;
}
</style>
