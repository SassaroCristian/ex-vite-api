<script>
export default {
    name: "breweryCard",
    props: {
        info: Object
    }
}
</script>

<template>
    <div class="card-wrapper">
        <div class="card">
            <h2>{{ info.name }}</h2>
            <p>{{ info.brewery_type }}</p>
            <p>{{ info.address_1 }}</p>
        </div>
    </div>
</template>

<style scoped>
.card-wrapper {
    padding: 1rem;
    width: 50%;
}

.card {
    padding: 1rem;
    background: orangered;
    color: white;
}
</style>

