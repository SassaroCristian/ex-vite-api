<script>
export default {
    name: "breweryCard",
    props: {
        info: Object
    }
}
</script>

<template>
    <div class="card w-96 h-44 bg-gradient-to-tr from-yellow-400 to-red-700 p-10 m-5">
        <h2 class=" text-2xl font-extrabold">{{ info.name }}</h2>
        <p class="text-lg">Brewery type: {{ info.brewery_type }}</p>
        <p>Address: {{ info.address_1 }}</p>
    </div>
</template>

<style scoped></style>

