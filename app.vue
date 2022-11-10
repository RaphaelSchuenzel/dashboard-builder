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
                :data="component"
            )
</template>

<script setup>
const components = [
    {
        chart: 'line'
    },
    {
        chart: 'bar'
    },
    {
        chart: 'line'
    },
    {
        chart: 'pie'
    },
    {
        chart: 'bar'
    }
]

const availableComponents = [
    {
        name: 'line',
        label: 'Line Chart'
    }
]
</script>


<style lang="sass">

</style>