<template>
    <block-view>
        <template #title>
            Work Experience
        </template>
        <template #body>
            <div class="mt-4">
                <div class="flex flex-col sm:flex-row sm:justify-between">
                    <template v-for="(exp, index) in Experience" :key="index">
                        <!-- Left View -->
                        <div class="mb-4 sm:mb-0 flex-shrink-0">
                            <p class="mb-1 text-xl font-bold tracking-tight text-slate-500" v-text="exp.LeftView.Company"/>
                            <p class="mb-1 text-slate-500" v-text="exp.LeftView.Position"/>
                            <p class="text-slate-400" v-text="exp.LeftView.Timespan"/>
                        </div>
                        <!-- Right View -->
                        <div class="mb-4 sm:ml-6 sm:mb-0">
                            <p class="text-xl font-bold tracking-tight text-slate-500" v-text="exp.RightView.Title"/>
                            <p class="mb-1 text-slate-400" v-text="exp.RightView.TimePosition"/>
                            <span v-html="exp.RightView.Description"></span>
                            <p class="mb-1 text-xl font-bold tracking-tight text-slate-500 mt-2">
                                What did I do
                            </p>
                            <ul class="list-disc mb-4">
                                <div class="pl-8">
                                    <template v-for="list in exp.RightView.Lists" :key="list">
                                        <li v-text="list"/>
                                    </template>
                                </div>
                            </ul>
                            <p v-text="exp.RightView.TechTitle" class="mb-1 text-xl font-bold tracking-tight text-slate-500"/>
                            <p>{{ exp.RightView.TechStack.join(", ") }}</p>
                            <hr class="mt-5">
                        </div>
                    </template>
                    <div class="hidden sm:block"></div>
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