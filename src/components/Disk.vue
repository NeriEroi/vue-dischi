<template>
<div class="container">

    <div class="disk_cont">
               
        <div class="img_cont">
            <img :src="info.poster" alt="info.author">
        </div>
        <h5>{{ info.title }}</h5>
        <div>{{ info.author }}</div>
        <div>{{ info.year }}</div>

    </div>

</div>
    
</template>

<script>

export default {
    name: 'Disk',
    props: ['info']
}
</script>

<style scoped lang="scss">
@import "../style/generals";
@import "../style/vars";

.container {
    width: calc(100% / 5);

    .disk_cont {
        width: 150px;
        height: 200px;
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 10px;
        background-color: $light;
        margin: 5px;

        .img_cont {
            width: 90%;
            height: 90%;

            img {
                width: 100%;
                height: 100%;
            }
        }
    }
}
  

</style>