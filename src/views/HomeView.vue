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
            `
            Full stack web developer and junior mobile software engineer with a positive attitude 
            that is always looking forward to find new ways to become a better engineer.
            `,
            `
            Strong history of problem solving and finding practical solutions within projects. 
            Experience with multiple projects within the few months of employment in collaboration with the IT team.
            `
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
                RightView: [
                    {
                        Title       :   'Bundle Product Project Development',
                        TimePosition:   '2022.9 - Present',
                        Description :   `
                            <p>Created bundle product module with</p>
                        `,
                        Lists       :   [
                            'Independently worked on the project before deployment.',
                        ],
                        TechTitle   :   'Tech Stack',
                        TechStack   :   ['Vue.js','Laravel','SQL','AJAX','JavaScript']
                    },
                    {
                        Title       :   'Appointment Booking Project Development',
                        TimePosition:   '2022.5 - 2022.10',
                        Description :   `
                            <p>I have had the opportunity to create a new appointment booking project using
                            Vuetify Calendar API and Vue.js. In order to do this, I first had to design and
                            implement complex tables in the database to store and manage calendar events.</p>
                            
                            <p class="mt-1">Additionally, I developed complex date and time logic to replicate Google's time and date 
                            format when users drag appointments, with the aim of enhancing the user interface and creating 
                            a more intuitive user experience.</p>
                            
                            <p class="mt-1">Through this work, I was able to apply my expertise in front-end and back-end 
                            development by using range of technical skills to deliver high-quality features and enhancements
                            that meet a user's needs.</p>
                        `,
                        Lists       :   [
                            'Independently worked on the project before deployment.',
                            'Designed and implemented the calendar module using Vuetify and Vue.js.',
                            'Designed the table database on how should the system save the events, and every other records.',
                            'Created the project by using a modular system, a package for Laravel created by nwidart.',
                            'Used a third party JavaScript library called "Moment.js" for the time and date formatting and calculation.'
                        ],
                        TechTitle   :   'Tech Stack',
                        TechStack   :   ['Vue.js','Laravel','SQL','AJAX','JavaScript']
                    },
                    {
                        Title       :   'Backend Internship',
                        TimePosition:   '2022.5 - 2022.10',
                        Description :   `
                            <p>
                                Quickly learned Laravel framework and Vues,js JavaScript framework without prior experience and 
                                fixed all bugs inside the staging server.
                            </p>
                            
                            <p class="mt-1">
                                After I fixed my first bug during the first week of the internship, I quickly adapted and began 
                                fixing live server bugs and issues at a fast pace.
                            </p>
                        `,
                        Lists       :   [
                            'Tested the website both front-end and back-end.',
                            'Fixed mostly bugs from staging server.',
                            'Fixed a lot of live server bugs and issues in a short span of time.',
                            'Able to deploy patches very quickly for testing phase.'
                        ],
                        TechTitle   :   'Tech Stack',
                        TechStack   :   ['Vue.js','Laravel','SQL','AJAX','JavaScript']
                    }
                ]
            },
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
