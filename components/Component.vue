<template lang="pug">
.component.bg-gray-50.mx-6.my-4.p-4
    h1 {{ $attrs.component.name }}

    BarChart(
        v-if="$attrs.component.chart === 'bar'"
        :data="$attrs.component.data"
    )

    PieChart(
        v-else-if="$attrs.component.chart === 'pie'"
        :data="$attrs.component.data"
    )
</template>

<script setup>
import BarChart from './charts/barChart'
import PieChart from './charts/pieChart'
</script>