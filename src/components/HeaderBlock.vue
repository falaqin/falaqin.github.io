<template>
    <block-view>
        <template #title>Falaqin, software engineer.</template>
        <template #body>
            <div class="mt-4">
                <div class="grid grid-cols-3 gap-4">
                    <div>
                        <img
                            src="../assets/pfp.jpeg"
                            alt="pfp"
                            width="200"
                            class="rounded-lg"
                        >
                    </div>
                    <div class="col-span-2">
                        <!-- Contacts -->
                        <div>
                            <span class="mb-2 text-xl font-bold tracking-tight text-slate-600" v-text="'Contact'"/>
                            <p><email-icon/>&nbsp;
                                <a
                                    target="_blank"
                                    class="underline"
                                    :href="EmailLink.link"
                                    v-text="EmailLink.name"
                                />
                            </p>

                            <p><home-icon/>&nbsp; KL, Malaysia.</p>
                        </div>

                        <!-- Socials -->
                        <div class="mt-6">
                            <span class="mb-2 text-xl font-bold tracking-tight text-slate-600" v-text="'Socials'"/>
                            <p v-if="SocialLink.linkedin">
                                <linkedin-icon/>&nbsp;
                                <a
                                    :href="SocialLink.linkedin.link"
                                    class="underline"
                                    v-text="SocialLink.linkedin.title"
                                />
                            </p>

                            <p v-if="SocialLink.github">
                                <github-icon/>&nbsp;
                                <a
                                    :href="SocialLink.github.link"
                                    class="underline"
                                    v-text="SocialLink.github.title"
                                />
                            </p>
                        </div>

                        <!-- Resume Download -->
                        <div class="mt-6">
                            <span class="mb-2 text-xl font-bold tracking-tight text-slate-600" v-text="'Resume'"/>

                            <p v-if="ResumeLink.resume">
                                <AccountCircleIcon/>&nbsp;
                                <a
                                    :href="ResumeLink.resume.link"
                                    class="underline"
                                    v-text="ResumeLink.resume.title"
                                    download
                                />
                            </p>
                        </div>
                    </div>
                </div>
            </div>
        </template>
    </block-view>
</template>

<script>
import { ref } from "vue";
import BlockView from "@/components/BlockView.vue";
import EmailIcon from 'vue-material-design-icons/Email.vue'
import LinkedinIcon from 'vue-material-design-icons/Linkedin.vue'
import GithubIcon from 'vue-material-design-icons/Github.vue'
import HomeIcon from 'vue-material-design-icons/Home.vue'
import AccountCircleIcon from 'vue-material-design-icons/AccountCircle.vue'
import 'vue-material-design-icons/styles.css';
export default {
    name: "HeaderBlock",
    components: { BlockView, EmailIcon, LinkedinIcon, GithubIcon, HomeIcon, AccountCircleIcon },
    props: ['email', 'social', 'resume'],

    setup(props) {
        let EmailLink = ref(props.email)
        let SocialLink = ref(props.social)
        let ResumeLink = ref(props.resume)

        return {
            EmailLink, SocialLink, ResumeLink
        }
    }
}
</script>