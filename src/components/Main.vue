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