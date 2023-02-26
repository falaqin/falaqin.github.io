<template>
    <block-view>
        <template #title>
            Work Experience
        </template>
        <template #body>
            <div class="mt-4">
                <div class="flex flex-col sm:flex-row sm:justify-between">
                    <div class="mb-4 sm:mb-0 flex-shrink-0">
                        <p class="mb-2 text-xl font-bold tracking-tight text-slate-500">Company Here</p>
                        <p class="text-slate-500">Frontend Developer</p>
                    </div>
                    <div class="mb-4 sm:ml-4 sm:mb-0">
                        <p class="mb-2 text-xl font-bold tracking-tight text-slate-500">
                            Very Long Text Here
                        </p>
                        <p class="sm:mb-0">
                            Another Very Long Description Here
                        </p>
                        <p class="mb-2 text-xl font-bold tracking-tight text-slate-500 mt-2">
                            What did I do
                            <!-- TODO loop list -->
                        </p>
                    </div>
                    <div class="hidden sm:block"></div> <!-- Empty grid column to fill in the gap -->
                </div>
            </div>
        </template>
    </block-view>
</template>

<script>
import BlockView from "@/components/BlockView.vue";
export default {
    name: "ExperienceBlock",
    components: {BlockView}
}
</script>

<style scoped>

</style>