<template>
<div class="grid md:grid-cols-3 gap-4">
    <!-- Box 1 -->
    <div class="shadow-md bg-blue-100 p-10 text-center rounded">
        <h3 class="text-3xl text-blue-900 font-bold mb-4">
            Cases
        </h3>
        <div class="text-2xl mb-4">
            <span class="font-bold">New: </span>
            {{ commaDelimiter(stats.NewConfirmed) }}
        </div>
        <div class="text-2xl mb-4">
            <span class="font-bold">Total: </span>
            {{ commaDelimiter(stats.TotalConfirmed) }}
        </div>
    </div>
    <!-- Box 2 -->
    <div class="shadow-md bg-purple-100 p-10 text-center rounded">
        <h3 class="text-3xl text-purple-900 font-bold mb-4">
            Deaths
        </h3>
        <div class="text-2xl mb-4">
            <span class="font-bold">New: </span>
            {{ commaDelimiter(stats.NewDeaths) }}
        </div>
        <div class="text-2xl mb-4">
            <span class="font-bold">Total: </span>
            {{ commaDelimiter(stats.TotalDeaths) }}
        </div>
    </div>
    <!-- Box 3 -->
    <div class="shadow-md bg-green-100 p-10 text-center rounded">
        <h3 class="text-3xl text-green-900 font-bold mb-4">
            Recoveries
        </h3>
        <div class="text-2xl mb-4">
            <span class="font-bold">New: </span>
            {{ commaDelimiter(stats.NewRecovered) }}
        </div>
        <div class="text-2xl mb-4">
            <span class="font-bold">Total: </span>
            {{ commaDelimiter(stats.TotalRecovered) }}
        </div>
    </div>
</div>    
</template>

<script>
export default {
    name: 'DataBoxes',
    props: {
        stats: Object,
    },
    methods: {
        commaDelimiter: function(num) {
            return num.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ",");
        }
    }
}
</script>