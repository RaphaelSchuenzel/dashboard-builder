<template lang="pug">
#dashboard.h-screen.w-screen.bg-gray-200
    .bg-gray-50
        .flex.items-center.justify-between.mx-6.px-6.py-4
            p ACME

            a.border-2.p-4 Add Component

    .mx-6.mt-8
        #components.grid.grid-cols-4
            Component(
                v-for="component in components"
                :component="component"
            )
</template>

<script setup>
const components = [
    {
        name: 'Monthly Profit',
        chart: 'line',
        data: [{x: 10, y: 20}, {x: 15, y: null}, {x: 20, y: 10}],
    },
    {
        name: 'Average Price',
        chart: 'bar',
        data: [{x: 10, y: 20}, {x: 15, y: null}, {x: 20, y: 10}],
    },
    {
        name: 'Sales per Month',
        chart: 'line',
        data: [{x: 10, y: 20}, {x: 15, y: null}, {x: 20, y: 10}],
    },
    {
        name: 'Monthly Revenue',
        chart: 'pie',
        data: [{x: 10, y: 20}, {x: 15, y: null}, {x: 20, y: 10}],
    },
    {
        name: 'Example',
        chart: 'bar',
        data: [{x: 10, y: 20}, {x: 15, y: null}, {x: 20, y: 10}],
    }
]

const availableCharts = [
    {
        name: 'line',
        label: 'Line Chart'
    }
]
</script>


<style lang="sass">

</style>