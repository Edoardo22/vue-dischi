<template>
    <div>
        <div class="fluid-container bg-secondary py-3 d-flex justify-content-between">
            <img class="logoSpoty ms-4 " src="img/spotify-logo.png" alt="">
            <form class="d-flex">
                <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
                <button class="btn btn-outline-success" type="submit">Search</button>
            </form>
        </div>
        <div class="container-fluid bg-main py-5 d-flex d-flex justify-content-center">
            <div class="container row row-cols-6 ">
                <div class="card col m-3 bg-secondary" v-for="(album, i) in dischi" :key="i">
                    <img :src="album.poster" class=" card-img-top" alt="">
                    <div class="card-body">
                        <h5 class="card-title">{{ album.title }}</h5>
                        <p class="card-text">{{ album.author }}</p>
                        <p class="card-text"> {{ album.year }}</p>

                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import axios from "axios";
export default {
    name: 'MainSite',
    data() {
        return {
            urlDischi: "https://flynn.boolean.careers/exercises/api/array/music",
            dischi: [],
        }
    },
    methods: {
        fetchData() {
            axios
                .get(this.urlDischi)
                .then(response => {
                    this.dischi = response.data.response;
                })
        },
    },
    mounted() {
        this.fetchData();
    },
}
</script>

<style>
.logoSpoty {
    width: 60px;
    height: 60px;
}

.bg-main {
    background-color: rgb(30, 45, 59);

}
</style>