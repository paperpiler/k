<template>
    <center>
        <div id="SearchBar">
        <textarea
            type="text"
            style="font-family: Source Code Pro"
            placeholder="Enter post..."
            class="rsearch"
            id="newformatf"
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
            var currentpost = document.getElementById('newformatf').value;

            /* remove a tag that might sneak in */
            currentpost = currentpost.replace("[ Photo ]\n", "");
            currentpost = currentpost.replace("[ Video ]\n", "");
            currentpost = currentpost.replace("[ GIF ]\n", "");

            /* warn for removal of changelog */
            currentpost = currentpost.replace(/Changelog:/, "CHANGE ME HEREE Changelog:");

            /* move hashtags to the start */ 
            var hashtags = currentpost.match(/.*?$/);
            currentpost = currentpost.replace(new RegExp("\n?\n?" + hashtags), "");
            currentpost = hashtags + "\n" + currentpost;

            /* fetch rom specific details */
            var status = currentpost.match(/Status: (.*)/);
            var androidv = currentpost.match(/Android: (.*)/);
            var size = currentpost.match(/Size: (.*)/);
            var updated = currentpost.match(/Updated: (.*)/);
            var by = currentpost.match(/By: (.*)/);
            var support = currentpost.match(/Support Group: ?(.*)/);

            /* strip new format detail items */
            currentpost = currentpost.replace(new RegExp(status[0]), "");
            currentpost = currentpost.replace(new RegExp("\n?" + size[0]), "");
            currentpost = currentpost.replace(new RegExp("\n?" + updated[0]), "");
            currentpost = currentpost.replace(new RegExp("\n?" + by[0]), "");
            currentpost = currentpost.replace(new RegExp("\n?" + support[0]), "");

            /* bruh this bracket shit is gay af */
            currentpost = currentpost.replace(new RegExp("\n?" + androidv[0].replace("(", "\\(").replace(")", "\\)")), "");

            /* create the new header */
            currentpost = currentpost.split("\n");
            var newhead = "**" + currentpost[1] + " - " + status[1] + " | " + androidv[0].replace(":", "").replace(/\([A-Z]?[a-z]?\)/, "").replace(new RegExp(" $"), "") + "**";
            currentpost[1] = newhead;
            currentpost = currentpost.join("\n");

            /* insert update date */
            currentpost = currentpost.split("\n");
            currentpost.splice(2, 0, "**Updated:** " + "__" + updated[1] + "__");
            currentpost = currentpost.join("\n");

            /* remove credits section */
            currentpost = currentpost.split("\n");
            var clAt = -1;
            for(var i=0; i<parseInt(currentpost.length); i++){
                if(currentpost[i].includes("Credit") || currentpost[i].includes("Special Thanks")){
                    clAt = i;
                    break;
                }
            }

            if(clAt != -1){
                while(!currentpost[clAt]=="")
                    currentpost.splice(clAt, 1);
            }

            currentpost = currentpost.join("\n");

            /* replace channel and group links */
            currentpost = currentpost.replace("Updates Channel: @RedmiNote7ProUpdates", "**By** " + by[1]);
            currentpost = currentpost.replace("Main Group: @VioletDiscussion", "**Follow* @VioletOfficialUpdates\n**Join** @VioletOfficialChat");

            /* add link placeholders */
            currentpost = currentpost.split("\n");
            var last = parseInt(currentpost.length)-1;
            while(!currentpost[last] == "") last -= 1;
            currentpost.splice(last, 0, "▪️ [Support](https://t.me/" + support[1].replace("@", "") + ")");
            currentpost.splice(last, 0, "▪️ [Device Changelog](PUTLINKHERE)");
            currentpost.splice(last, 0, "▪️ [Source Changelog](PUTLINKHERE)");
            currentpost.splice(last, 0, "▪️ [Download](PUTLINKHERE) [" + size[1] + "]");
            currentpost = currentpost.join("\n");

            /* clean up duplicate newlines */
            currentpost = currentpost.replace(/\n\n/, "\n");

            /* finally apply the converted format to the text field */
            document.getElementById('newformatf').value = currentpost;
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
    text-align: left;
}

.rsubmit {
    width: 80vw;
    margin-top: 25px;
    border: 0vw;
}
</style>
