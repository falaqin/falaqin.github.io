<template>
    <block-view>
        <template #title>
            Education
        </template>
        <template #body>
            <div class="mt-4">
                <div class="flex flex-col sm:flex-row sm:justify-between">
                    <div class="w-full">
                        <template v-for="(edu, index) in Education" :key="index">
                        <!-- Left View -->
                        <div class="mb-5">
                            <div class="mb-4 sm:mb-0 flex-shrink-0">
                                <p class="mb-1 text-xl font-bold tracking-tight text-slate-700 underline" v-text="edu.LeftView.School" />
                                <p class="text-slate-500" v-text="edu.LeftView.Timespan" />
                            </div>
                        </div>
                        <!-- Right View -->
                        <template v-for="(view, index) in edu.RightView" :key="index">
                            <div class="mb-4 sm:ml-6 sm:mb-0">
                                <p class="text-xl font-bold tracking-tight text-slate-500" v-text="view.Course" />
                                <p class="mb-1 text-slate-400" v-text="view.TimePosition" />
                                
                                <ul class="list-disc mb-4">
                                    <div class="pl-8">
                                    <template v-for="list in view.Lists" :key="list">
                                        <li v-text="list" />
                                    </template>
                                    </div>
                                </ul>
                                
                                <hr class="my-5" />
                            </div>
                        </template>
                        </template>
                    </div>
                    
                </div>
            </div>
        </template>
    </block-view>
</template>

<script>
import BlockView from "@/components/BlockView.vue";
import {ref} from "vue";
export default {
    name: "EducationBlock",
    components: {BlockView},
    props: ['education'],

    setup(props) {
        let Education = ref(props.education)

        return {
            Education
        }
    }
}
</script>

<style scoped>

</style>