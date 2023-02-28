<template>
    <div class="flex items-center justify-center pb-16">
        <div class="row">
            <header-block
                :email="EmailLink"
                :social="SocialLink"/>
            <intro-block
                :intro="Introduction"/>
            <expertise-block
                :areas="ExpertiseAreas"/>
            <experience-block
                :experience="Experience"/>
            <div class="mt-6">
                <github-icon/> <a href="https://github.com/obake199/vue-resume" class="underline text-blue-300">Source Code</a>
            </div>
        </div>
    </div>
</template>

<script>
import {ref} from "vue";
import HeaderBlock from "@/components/HeaderBlock.vue";
import IntroBlock from "@/components/IntroBlock.vue";
import ExpertiseBlock from "@/components/ExpertiseBlock.vue";
import GithubIcon from 'vue-material-design-icons/Github.vue';
import ExperienceBlock from "@/components/ExperienceBlock.vue";
export default {
    name: 'HomeView',
    components: { GithubIcon, HeaderBlock, IntroBlock, ExpertiseBlock, ExperienceBlock },

    setup() {
        const gmailURL = new URL('https://mail.google.com/mail/u/0/')
        gmailURL.searchParams.set('to', 'falaqin.work@gmail.com') // recipient email
        gmailURL.searchParams.set('su', 'Software Engineer') // subject
        gmailURL.searchParams.set('body', 'BODY') // body
        gmailURL.searchParams.set('tf', 'cm') // fullscreen

        const EmailLink = ref({
            name    :   'falaqin.work@gmail.com',
            link    :   gmailURL
        })

        const SocialLink = ref({
            linkedin    :   {link: new URL('https://www.linkedin.com/in/falaqin/'), title: 'Falaqin'},
            github      :   {link: new URL('https://github.com/obake199'), title: 'obake199'}
        })

        const Introduction = ref([
            'Falaqin is a full stack web developer and a junior mobile software engineer.',
            'A positive-attitude, competitive software engineer that is always looking ' +
            'forward for new ways to grow into a better engineer.',
            'Has a very strong history of problem solving solutions within projects, handled ' +
            'multiple projects within few months of employment, while adept at identifying solutions in ' +
            'collaboration of IT team.',
        ])

        const ExpertiseAreas = ref([
            {title   :   'SQL'},
            {
                title   :   'Vue.js',
                desc    :
                    `<span class="mb-2 text-xl font-bold tracking-tight text-slate-500">Vue.js</span>
                        <ul class="list-disc mb-4">
                            <div class="pl-8">
                                <li>
                                    Made use of directives such as <span class="font-bold">reusable components</span>,
                                    and enhances company codebase by making everything more flexible to add new features.
                                </li>
                                <li>
                                    Experienced with Vuetify framework, on top of Vue.js.
                                </li>
                                <li>
                                    Single-handedly introduces and implemented Vue.js for a company's codebase on frontend,
                                    while fixing CSS issues during development.
                                </li>
                            </div>
                        </ul>
                    `
            },
            {
                title   :   'Laravel',
                desc    :   `
                    <span class="mb-2 text-xl font-bold tracking-tight text-slate-500">Laravel</span>
                    <ul class="list-disc mb-4">
                        <div class="pl-8">
                            <li>
                                Most comfortable with backend development, requiring intensive thinking and
                                problem-solving skills for development.
                            </li>
                            <li>
                                Created many codebase enhancements, such as Artisan commands for database backup if
                                needed patches, enhanced routing to follow REST API methods.
                            </li>
                            <li>
                                Implemented APIs on personal projects such as OpenAI API, Google API.
                            </li>
                        </div>
                    </ul>
                `
            },
            {title   :   'PHP'},
            {title   :   'AJAX'},
            {title   :   'jQuery'},
            {title   :   'Javascript'},
            {
                title: 'Typescript',
                desc:
                `
                    <span class="mb-2 text-xl font-bold tracking-tight text-slate-500">TypeScript</span>
                    <ul class="list-disc mb-4">
                        <div class="pl-8">
                            <li>
                                Implemented assigned projects from web to mobile application using Laravel and
                                Ionic-based frameworks.
                            </li>
                        </div>
                    </ul>
                `
            },
            {
                title   :   'Project Management',
                desc    :
                    `<span class="mb-2 text-xl font-bold tracking-tight text-slate-500">
                        Project Management
                    </span>

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
                    </ul>`
            },
        ])

        const Experience = ref([
            {
                LeftView: {
                    Company     :   'Bluevy PLT',
                    Position    :   'Full Stack Developer',
                    Timespan    :   '2022.3 - Present',
                },
                RightView: {
                    Title       :   'Calendar Module Development',
                    TimePosition:   '2022.7 - Present',
                    Description :   `
                        <p>As a developer with experience in calendar development, I have had the opportunity to create
                        a new calendar module using Vuetify and Vue.js. In order to do this, I first had to design and
                        implement complex tables in the database to store and manage calendar events. Additionally,
                        I developed complex date and time logic to replicate Google's time and date format when users
                        drag appointments, with the aim of enhancing the user interface and creating a more intuitive
                        user experience. Through this work, I was able to apply my expertise in front-end and back-end
                        development, and bring together a range of technical skills to deliver a high-quality calendar
                        module that meets user needs.</p>
                    `,
                    Lists       :   [
                        'Handled multiple projects.',
                        'Helped seniors with their project for both front end and back end',
                        'Migrated some functions from Option API to Composition API in Vue.js',
                        'Improved caching performance by creating interface for classes',
                        'Improved codebase by introducing MVC design pattern for blade.php pages.',
                        'Introduced better structured functions for better readability and maintainability.',
                        'Created new modules for enhancement by creating new directory, and uses existing controllers by inheritance.',
                        'Created multiple templates and reusable components in Vue.js, used by colleagues.',
                        'Patches database if there are inconsistencies by using custom Artisan command.'
                    ],
                    TechTitle   :   'Tech Stack',
                    TechStack   :   ['Vue.js','Laravel','SQL','AJAX','JavaScript']
                }
            }
        ])

        return {
            EmailLink,
            SocialLink,
            Introduction,
            ExpertiseAreas,
            Experience
        }
    }
}
</script>
