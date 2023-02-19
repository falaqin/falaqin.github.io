<template>
    <block-view>
        <template #title>
            Introduction
        </template>
        <template #body>
            <template v-for="(paragraph, index) in intro" :key="index">
                <p v-text="paragraph"/>
            </template>
        </template>
    </block-view>
</template>

<script>
import BlockView from "@/components/BlockView.vue";
export default {
    name: "IntroBlock",
    components: {BlockView},
    props: ['intro']
}
</script>