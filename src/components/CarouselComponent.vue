<script setup>

import { ref, onMounted, onBeforeUnmount, nextTick } from 'vue'

const items = ref([
    {
        title:'Hive Coworking Space',
        url:'https://images.unsplash.com/photo-1538688525198-9b88f6f53126?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1074&q=80'
    },
    {
        title:'Modern minimalist home design',
        url:'https://images.unsplash.com/photo-1586023492125-27b2c045efd7?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=958&q=80'
    },
    {
        title:'workspace',
        url:'https://images.unsplash.com/photo-1524758631624-e2822e304c36?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1170&q=80'
    },
    {
        title:'cat with window in wooster',
        url:'https://images.unsplash.com/photo-1493663284031-b7e3aefcae8e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1170&q=80'
    },
])

let carousel = null

onMounted(() =>{
    carousel = new Flickity( '#carousel', {
    });
})

onBeforeUnmount(() => {
    carousel.destroy()
})


function refresh_carousel(){

    //update carousel element here as required

    //
    carousel.destroy()
    nextTick(() =>{
        carousel = new Flickity( '#carousel', {});
    })
}

</script>
<template>
    <h1 class="text-2xl text-gray-900 text-center">Carousel</h1>
    <div class="mx-auto items" id="carousel">
        <div class=" item " :style="`background-image:url(${item.url})`" v-for="(item, index) in items" :key="index">
            <p class="pl-12 pr-12 pt-80 text-white font-bold ">{{ item.title }}</p>
        </div>
    </div>    

</template>

<style scoped>
.items{
    width: 400px;
    height:300px;
}

.item{
    width: 400px;
    height: 300px;
    background-color: gray;
    background-size: cover;
}

</style>
