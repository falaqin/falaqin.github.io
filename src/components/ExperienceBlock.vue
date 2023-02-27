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
                        <ul class="list-disc mb-4">
                            <div class="pl-8">
                                <li>
                                    Handled multiple projects within the span of under 8 months as a one-man army.
                                </li>
                                <li>
                                    Helped seniors with other big projects, implementing new functions.
                                </li>
                                <li>
                                    Enhancements for existing CRM system, such as <span class="font-bold">calendar and
                                    events system</span>.
                                </li>
                                <li>
                                    Ensuring flexibility of making appointments with contacts, and track
                                    record for each appointment.
                                </li>
                                <li>
                                    Development of <span class="font-bold">rental</span> items/products.
                                </li>
                                <li>
                                    The rental project has made use of
                                    <span class="font-bold">cron jobs and server-side shell commands</span>.
                                </li>
                            </div>
                        </ul>
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