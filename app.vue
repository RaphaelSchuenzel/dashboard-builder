<template lang="pug">
#dashboard
    a Add Component

    #components
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
    'Line Chart'
]
</script>


<style lang="sass">

</style>