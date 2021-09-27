<template>
  <div>
        <div class="row">
            
            <div class="logo_cont">
                <img src="../assets/img/logo-small.svg" alt="spotify logo">
            </div>

            <select v-model="genreFilter" @change="$emit('changedGenre', genreFilter)">
                <option value="">Select a disk</option>
                <option v-for="(genre, index) in genres" :key="index" :value="genre">
                    {{ genre }}
                </option>
            </select>

        </div>
  </div>
</template>

<script>


export default {
    name: 'Header',
    props: {
        genres: Array,
    },
    data() {
        return {
            genreFilter: '',
        }
    }
} 
</script>

<style scoped lang="scss">
@import "../style/generals";
@import "../style/vars";

    .row {
        width: 100%;
        height: 80px;
        background-color: $light;
        display: flex;
        justify-content: space-between;

        .logo_cont {
            width: 5%;
            height: 100%;
            display: flex;
            justify-content: center;
            align-items: center;

            img {
                width: 60%;
                height: 60%;
                object-fit: contain;
            }
        }

        select {
            margin: 25px;
            height: 30px;
        }
    }  
    
</style>