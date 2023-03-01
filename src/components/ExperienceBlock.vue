<template>
    <block-view>
        <template #title>
            Work Experience
        </template>
        <template #body>
            <div class="mt-4">
                <div class="flex flex-col sm:flex-row sm:justify-between">
                    <div class="w-full">
                        <template v-for="(exp, index) in Experience" :key="index">
                        <!-- Left View -->
                        <div class="mb-5">
                            <div class="mb-4 sm:mb-0 flex-shrink-0">
                                <p class="mb-1 text-xl font-bold tracking-tight text-slate-700 underline" v-text="exp.LeftView.Company" />
                                <p class="mb-1 text-slate-600" v-text="exp.LeftView.Position" />
                                <p class="text-slate-500" v-text="exp.LeftView.Timespan" />
                            </div>
                        </div>
                        <!-- Right View -->
                        <template v-for="(view, index) in exp.RightView" :key="index">
                            <div class="mb-4 sm:ml-6 sm:mb-0">
                                <p class="text-xl font-bold tracking-tight text-slate-500" v-text="view.Title" />
                                <p class="mb-1 text-slate-400" v-text="view.TimePosition" />
                                
                                <span v-html="view.Description"/>
                                <p class="mb-1 text-xl font-bold tracking-tight text-slate-500 mt-2">
                                    What did I do
                                </p>
                                
                                <ul class="list-disc mb-4">
                                    <div class="pl-8">
                                    <template v-for="list in view.Lists" :key="list">
                                        <li v-text="list" />
                                    </template>
                                    </div>
                                </ul>
                                
                                <p v-text="view.TechTitle" class="mb-1 text-xl font-bold tracking-tight text-slate-500" />
                                
                                <p>{{ view.TechStack.join(", ") }}</p>
                                
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
    name: "ExperienceBlock",
    components: {BlockView},
    props: ['experience'],

    setup(props) {
        let Experience = ref(props.experience)
        console.log(Experience.value)

        return {
            Experience
        }
    }
}
</script>

<style scoped>

</style>