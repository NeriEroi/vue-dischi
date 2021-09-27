<template>
    <div class="main">

        <Disk v-for="(disk, index) in disksList" :key="index" :info="disk"/>

    </div>
</template>

<script>
import axios from 'axios';
import Disk from './Disk.vue';


export default {
    name: 'Main',
    components: {
        Disk,
    },
    data() {
        return {
           APIUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
           disksList: [],
           genres: []
        }
    },
    created() {
        this.getDisks();
        this.getGenre();
    },
    methods: {
        getDisks() {
            axios
                .get(this.APIUrl)
                .then( res => {
                    // console.log(res.data.response);
                    this.disksList = res.data.response;
                });
        },
        getGenre() {
            axios
                .get(this.APIUrl)
                .then( res => {
                    // console.log(res.data.response);
                    this.disksList = res.data.response;

                    this.disksList.forEach((disk) => {
                        if (!this.genres.includes(disk.genre)) {
                            this.genres.push(disk.genre)
                        }
                    })
                });
                this.$emit("genresReady", this.genres)
        }
    }
}
</script>

<style scoped lang="scss">
@import "../style/generals";
@import "../style/vars";


.main {
    width: 60%;
    height: calc(100vh - 80px);
    margin: auto;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
}

</style>