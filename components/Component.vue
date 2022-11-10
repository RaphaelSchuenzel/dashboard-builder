<template lang="pug">
.component.bg-gray-50.mx-6.my-4.p-4
    h1 {{ $attrs.component.name }}

    Bar(
        :chart-data="$attrs.component.data"
        v-if="$attrs.component.chart === 'bar'"
    )
</template>

<script setup>
import { Bar } from 'vue-chartjs'
</script>