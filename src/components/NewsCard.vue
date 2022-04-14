<template>
    <div class="card">
        <img :src="img" :alt="title">
        <h3 class="title" @click="$emit('action')">{{title}}</h3>
    </div>
</template>


<script>
export default {
    props: {
        img: {
            type: String,
            default: () => 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQW6wRWOjhYe9HP1hvqWiY_x4tDvhbtNcvKUw&usqp=CAU'
        },
        title: {
          type: String,
          required: true,
        }
    }
}
</script>


<style lang="scss">
.card {
    width: 350px;
    height: 400px;
    border-radius: 20px;
    overflow: hidden;
    position: relative;
    &::after{
        content: "";
        position: absolute;
        left: 0;
        top: 0;
        width: 100%;
        height: 100%;
        background: linear-gradient(transparent, rgba(0,0,0, 0.8));
        z-index: 1;
    }
    img{
        position: absolute;
        left: 0;
        top: 0;
        width: 100%;
        height: 100%;
        z-index: 1;
    }
    .title {
        position: absolute;
        left: 0;
        bottom: 0;
        cursor: pointer;
        width: 100%;
        z-index: 2;
        padding: 20px;
    }
}
</style>