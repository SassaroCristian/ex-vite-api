<script>
export default {
    name: "breweryCard",
    props: {
        info: Object
    }
}
</script>

<template>
    <div class="card w-96 bg-gradient-to-tr from-orange-400 to-red-700 p-10 m-5">
        <h2 class="font-bold ">{{ info.name }}</h2>
        <p>Brewery type: {{ info.brewery_type }}</p>
        <p>Address: {{ info.address_1 }}</p>
    </div>
</template>

<style scoped></style>

