<template>
    <center>
        <div id="SearchBar">
        <textarea
            type="text"
            style="font-family: Source Code Pro"
            placeholder="Enter post..."
            class="rsearch"
        />
    </div>

    <b-button block variant="primary" class="rsubmit" v-on:click="convert">Convert</b-button>
    </center>
</template>

<script>
export default {
    name: "SearchBar",
    methods: {
        convert: () => {
            alert('bruh working!');
        }
    }
};
</script>

<style scoped>
.rsearch {
    border-radius: 10px;
    width: 100vw;
    height: 500px;
    margin-top: 20px;
    border: 0vw;
    text-indent: 10px;
    text-align: left;
}

.rsubmit {
    width: 80vw;
    margin-top: 25px;
    border: 0vw;
}
</style>
