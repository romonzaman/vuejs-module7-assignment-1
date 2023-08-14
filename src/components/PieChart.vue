<script setup>
import { onBeforeMount, onMounted, onBeforeUnmount, ref } from 'vue';

let pieChart = null

// chart data
const data = {
    labels: [
        'Red',
        'Green',
        'Blue'
    ],
    datasets: [{
        data: [30, 40, 30],
        backgroundColor: [
            'red',
            'green',
            'blue'
        ],
        hoverOffset: 4
    }]
};

// Pie chart configuration
const pieConfig = {
    type: 'pie',
    data: data,
    options: {
        responsive: true
    }
};


onMounted(() => {
    // Get a reference to the canvas element
    const pieCtx = document.getElementById('pieChart').getContext('2d');
    // Create the pie chart
    pieChart = new Chart(pieCtx, pieConfig);
})

onBeforeUnmount(() => {
    //cleanup
    pieChart.destory()
})


/*
this function will allow use to reload piechart
*/
function updateChart() {
    //change pie chart data here
    //
    //
    pieChart.update()
}

</script>

<template>
    <div class="flex flex-col items-center justify-center">
        <div class="w-64">
            <h1 class="text-2xl text-gray-900 text-center">Pie Chart</h1>
            <canvas id="pieChart"></canvas>
        </div>
    </div>

</template>

<style scoped></style>
