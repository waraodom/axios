<template>
<div>
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/2/2a/ITunes_12.2_logo.png/768px-ITunes_12.2_logo.png" alt="" height="100px" width="300px" class="img-fluid mx-auto" />
    <br />
    <br />
    <div class="row">
        <div class="col">
        </div>
        <div class="col">
            <input class="form-control ds-input " type=" text" v-model="keyword" placeholder="Search......."/>
            <br />
            <button @click="searchData" class="btn btn-primary">Search Music</button>
            <!--{{resultData}} -->
        </div>
        <div class="col">
        </div>
    </div>
    <br />
    <br />
    <div class="row">
        <div class="col-sm"></div>
        <div class="col-sm">
            <b-card-group columns>
                <div v-for="data in resultData" :key="data.trackId">
                    <b-card :title="data.title" :img-src="data.artworkUrl100" img-alt="Image" img-top tag="article" style="max-width: 25rem;" class="mb-2">
                        <b-card-text>{{ data.trackName }}</b-card-text>
                        <b-card-text>{{ data.artistName }}</b-card-text>
                        <audio controls >
                            <source :src="data.previewUrl" type="audio/mpeg" />
                        </audio>
                        <b-button :href="data.trackViewUrl" variant="danger">Play</b-button>
                    </b-card>
                </div>
            </b-card-group>
        </div>
        <div class="col-sm"></div>
    </div>
</div>
</template>

<script>
import axios from "axios";
export default {
    data() {
        return {
            resultData: null,
            keyword: "",
        };
    },
    methods: {
        searchData() {
            axios
                .get(
                    "https://itunes.apple.com/search?term=" + this.keyword + "&limit=15"
                )
                .then((response) => {
                    this.resultData = response.data.results;
                })
                .catch((err) => {
                    console.log(err);
                });
        },
    },
};
</script>

<style>
.card {
    background-image: url('https://i.pinimg.com/originals/38/50/10/38501026bec50e2e39d7b7023d7d248c.png');
}
</style>
