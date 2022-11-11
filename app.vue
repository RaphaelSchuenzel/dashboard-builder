<template lang="pug">
#dashboard.bg-gray-200
    .bg-gray-50
        .flex.items-center.justify-between.mx-6.px-6.py-4
            p ACME

            a.border-2.p-4 Add Component

    .mx-6.py-8
        #components.grid.grid-cols-4
            Component(
                v-for="component in components"
                :component="component"
            )
</template>

<script setup>
const components = [
    {
        name: 'Orders per Year',
        chart: 'bar',
        data: {
            labels: ['2020', '2021'],
            datasets: [
                {
                    label: 'Orders',
                    data: [4000, 2000]
                }
            ],
        },
    },
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