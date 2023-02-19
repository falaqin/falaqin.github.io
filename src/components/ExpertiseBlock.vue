<template>
    <block-view>
        <template #title>
            Areas of Expertise
        </template>
        <template #body>
            <template v-for="(tags, index) in areas" :key="index">
                <span
                    class="bg-indigo-100 text-indigo-800 text-xs font-medium mr-2 px-2.5 py-0.5
                    rounded dark:bg-gray-700 dark:text-indigo-400 border border-indigo-400"
                    v-text="tags"
                />
            </template>
        </template>
    </block-view>
</template>

<script>
import BlockView from "@/components/BlockView.vue";
export default {
    name: "ExpertiseBlock",
    components: {BlockView},
    props: ['areas']
}
</script>

<style scoped>

</style>