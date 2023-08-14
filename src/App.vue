<script setup>
import CarouselComponent from './components/CarouselComponent.vue'
import PieChart from './components/PieChart.vue'

</script>

<template>

    <div class="h-screen">
        <div class="flex flex-col xs:flex-row  justify-center items-center">
            <div>
                <CarouselComponent />
            </div>
            <div class="flex justify-center items-center">
                <PieChart class="mt-10"/>
            </div>
        </div>


    </div>

</template>

<style scoped>
</style>