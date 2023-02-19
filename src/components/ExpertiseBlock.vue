<template>
    <block-view>
        <template #title>
            Areas of Expertise
        </template>
        <template #body>
            <div class="grid grid-cols-3 gap-2 text-center">
                <template v-for="(tags, index) in areas" :key="index">
                <span
                    class="bg-indigo-100 text-indigo-800 text-xs font-medium mr-2 px-2.5 py-0.5
                    rounded border border-indigo-400"
                    v-text="tags.title"
                />
                </template>
            </div>

            <hr class="my-4">

            <template v-for="(tags, index) in areas" :key="index">
                <span v-if="tags.desc" v-html="tags.desc"/>
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