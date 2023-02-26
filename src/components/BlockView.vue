<template>
    <div class="col p-6 rounded-lg shadow-lg bg-white text-left m-auto mt-6 max-w-3xl">
        <h4 class="mb-2 text-3xl font-bold tracking-tight text-cyan-700">
            <slot name="title" />
        </h4>

        <slot name="body"/>
    </div>
</template>

<script>
export default {
  name: "BlockView"
}
</script>

<style scoped>

</style>