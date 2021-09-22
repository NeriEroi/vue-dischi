<template>
    <div class="main">

        <Disk v-for="(disk, index) in disksList" :key="index" :info="disk"/>

    </div>
</template>

<script>
import axios from 'axios';
import Disk from './Disk.vue'
export default {
    name: 'Main',
    components: {
        Disk
    },
    data() {
        return {
           APIUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
           disksList: []
        }
    },
    created() {
        this.getDisks();
    },
    methods: {
        getDisks() {
            axios
                .get(this.APIUrl)
                .then( res => {
                    // console.log(res.data.response);
                    this.disksList = res.data.response;
                })
        }
    }
}
</script>

<style>
.main {
    width: 100%;
    height: 90vh;
    background-color: darkgreen;
}

</style>