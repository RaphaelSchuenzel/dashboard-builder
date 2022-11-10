<template lang="pug">
#dashboard.container.mx-auto
    a Add Component

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