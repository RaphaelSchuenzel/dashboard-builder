<template lang="pug">
#dashboard.bg-gray-200.min-h-screen
    .bg-gray-50
        .flex.items-center.justify-between.mx-6.px-6.py-4
            p ACME

            a.border-2.p-4.opacity-20 Add Component

    .mx-6.py-8
        #components.grid.grid-cols-4
            Component(
                v-for="component in components"
                :component="component"
            )
</template>

<script lang="ts">
import _ from 'lodash'

const getDataSet = () => import('~/static/data/us-sales.json').then(m => m.default || m)

export default defineNuxtComponent({
    async asyncData() {
        const dataSet = await getDataSet()

        return { dataSet }
    },
    data () {
        return {
            components: [
                // [bar] Total orders per year (sum(orders):year)
                {
                    name: 'Orders per Year',
                    chart: 'bar',
                    data: this.getChartData(this.dataSet, 'year', 'Orders')
                },

                // todo: [bar] Revenue per year (sum(order.price):year)

                // todo: [pie] Orders by payment method (orders:payment_method)

                // todo: [bar] Orders by region (orders:region)

                // todo: [pie] Average order discount (orders:discount)
            ],

            // todo: component builder chart options
            /* availableCharts: [
                {
                    name: 'line',
                    label: 'Line Chart'
                }
            ] */
        }
    },
    methods: {
        getChartData(arr: Array<Object>, key: String, label: String) {
            const groupedArr = _(arr)
                .groupBy(key)
                .value()

            const labels = Object.keys(groupedArr)
            const data = []

            Object.keys(groupedArr).forEach(key => {
                data.push(groupedArr[key].length)
            })

            const datasets = [
                {
                    label,
                    data
                }
            ]

            return {
                labels,
                datasets
            }
        },
    },
})
</script>

<style lang="sass"></style>
