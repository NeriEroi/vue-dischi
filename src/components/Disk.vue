<template>
<div class="container">

    <div class="disk_cont">
               
        <div class="img_cont">
        <img class="image" :src="info.poster" alt="info.author">
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

<style>
.disk_cont {
    display: flex;
    flex-direction: column;
    align-items: center;
} .img_cont {
    width: 8%;
    height: 8%;
} .image {
    width: 100%;
    height: 100%;
}

</style>