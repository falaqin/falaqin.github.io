<template>
    <div class="flex items-center justify-center pb-16">
        <div class="row">
            <div>
                <header-block
                    :email="EmailLink"
                    :social="SocialLink"
                    :resume="ResumeLink"/>
                <intro-block
                    :intro="Introduction"/>
                <expertise-block
                    :areas="ExpertiseAreas"/>
                <experience-block
                    :experience="Experience"/>
                <education-block
                    :education="Education"/>
                <div class="mt-6">
                    <github-icon/> <a href="https://github.com/obake199/vue-resume" class="underline text-blue-300">Source Code</a>
                </div>
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
import EducationBlock from "@/components/EducationBlock.vue";
export default {
    name: 'HomeView',
    components: { 
        GithubIcon, 
        HeaderBlock, 
        IntroBlock, 
        ExpertiseBlock, 
        ExperienceBlock, 
        EducationBlock 
    },

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

        const ResumeLink = ref({
            resume  :   {link: `${process.env.BASE_URL}files/Resume.pdf`, title: 'Download Resume'}
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
                        Title       :   'Jobcase Module Project Development',
                        TimePosition:   '2023.1 - 2023.2',
                        Description :   `
                            <p>
                                Helped a senior engineer for the development for the frontend dashboard for agents.
                                The frontend dashboard was developed by implementing Vue.js inside the Laravel Blade file,
                                to improve the user experience.
                            </p>

                            <p class='mt-1'>
                                The goal was to make the frontend dashboard more accessible to the agents, and make it more
                                flexible to navigate and interact with the interface.
                            </p>

                            <p class='mt-1'>
                                Also helped with backend for common functions and increased scalability by making it more
                                by using inheritance.
                            </p>
                        `,
                        Lists       :   [
                            'Fixed compatibility issues of CSS for front end to implement Vue.js.',
                            'Enhanced user experience by the use of Vue.js and Axios package.'
                        ],
                        TechTitle   :   'Tech Stack',
                        TechStack   :   ['Vue.js','Laravel Framework','SQL','JavaScript']
                    },
                    {
                        Title       :   'Rental Product Project Development',
                        TimePosition:   '2022.10 - 2023.2',
                        Description :   `
                            <p>
                                This project was made with various coding pattern, such as inheritance, traits, middleware,
                                facade, service providers, repositories for interface, and observers to observe changes in a
                                model.
                            </p>

                            <p class="mt-2">
                                The project was only for the backend with future plans for the frontend, 
                                to provide flexibility and logs all the inventory transactions for clients to be able to
                                track how much inventory they have at the time, and the possibility of renting a product 
                                on a certain date.
                            </p>

                            <p class="mt-1">
                                It's not only for creating orders, but also related to the appointment
                                booking project, and it's very important that it is compatible with CRM module,
                                and users can book an appointment with any chosen product types or rental products.
                            </p>
                        `,
                        Lists       :   [
                            'Compatible with order module and CRM module.',
                            'Used various coding patterns to enhance scalability and performance.',
                            'Made it modular and robust for future enhancements.',
                            'Upgraded older related packages such as vue datepickers.',
                            'Used repositories and observers code pattern for caching to improve performance.',
                            'Implemented complicated time and date system by using Carbon for cron jobs.'
                        ],
                        TechTitle   :   'Tech Stack',
                        TechStack   :   ['Vue.js','Laravel Framework','SQL','JavaScript', 'Ajax', 'Redis']
                    },
                    {
                        Title       :   'Bundle Product Project Development',
                        TimePosition:   '2022.9 - On hold',
                        Description :   `
                            <p>
                                Created the module by using a slightly different approach from the other development,
                                by using Laravel's database migration feature, and had to do a lot of scribbling
                                to ensure the flow is easy to understand by the user themselves as well.
                            </p>

                            <p class="mt-1">
                                The idea of this project was to include multiple products in one
                                singular product container, and the backend user is able to choose which input type they would
                                like to use for the front end. For example: dropdown menu, multiple selection, radio buttons,
                                and checkboxes.
                            </p>

                            <p class="mt-1">This project was put on hold to prioritize other project.</p>
                        `,
                        Lists       :   [
                            'Independently worked on the project.',
                            'Created new tables with Laravel Migration.',
                            'Reused older functions and made them modular for better reusable.',
                            'Made it fully functional on mobile as well with Angular on Ionic framework.',
                            'Developed with compatibility with other functions related to money and credit points transactions.'
                        ],
                        TechTitle   :   'Tech Stack',
                        TechStack   :   ['Vue.js','Laravel Framework','SQL','Angular','TypeScript','Angular','Ionic Framework']
                    },
                    {
                        Title       :   'Appointment Booking Project Development',
                        TimePosition:   '2022.5 - 2022.10',
                        Description :   `
                            <p>
                                I have had the opportunity to create a new appointment booking project using
                                Vuetify Calendar API and Vue.js. In order to do this, I first had to design and
                                implement complex tables in the database to store and manage calendar events.
                            </p>
                            
                            <p class="mt-1">
                                Additionally, I developed complex date and time logic to replicate Google's time and date 
                                format when users drag appointments, with the aim of enhancing the user interface and creating 
                                a more intuitive user experience.
                            </p>
                            
                            <p class="mt-1">
                                Through this work, I was able to apply my expertise in front-end and back-end 
                                development by using range of technical skills to deliver high-quality features and enhancements
                                that meet a user's needs.
                            </p>
                        `,
                        Lists       :   [
                            'Independently worked on the project before deployment.',
                            'Designed and implemented the calendar module using Vuetify and Vue.js.',
                            'Designed the table database on how should the system save the events, and every other records.',
                            'Created the project by using a modular system, a package for Laravel created by nwidart.',
                            'Used a third party JavaScript library called "Moment.js" for the time and date formatting and calculation.'
                        ],
                        TechTitle   :   'Tech Stack',
                        TechStack   :   ['Vue.js','Laravel Framework','SQL','Vuetify','JavaScript']
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
                        TechStack   :   ['Vue.js','Laravel Framework','SQL','AJAX','JavaScript']
                    }
                ]
            },
        ])

        const Education = ref([
            {
                LeftView: {
                    School      :   'Politeknik Sultan Mizan Zainal Abidin',
                    Timespan    :   '2019.6 - 2022.3',
                },
                RightView: [
                    {
                        Course      :   'Diploma of Digital Technology',
                        TimePosition:   '2019.6 - 2022.3',
                        Lists       :   [
                            'Acquired 3.93 CGPA.',
                            'Gained leadership role in Multimedia Club for POLITV.',
                            'Second runner-up in CAMP21: Synergizing Literacies 2019.',
                            'Participated in various events as Master Ceremony.'
                        ]
                    }
                ]
            },
            {
                LeftView: {
                    School      :   'Sultan Ismail College',
                    Timespan    :   '2014.1 - 2018.12',
                },
                RightView: [
                    {
                        Course      :   'Pure Science Stream (SPM)',
                        TimePosition:   '2014.1 - 2018.12',
                        Lists       :   [
                            '2A (English, Mathematics).',
                            '1B+ (Pendidikan Islam).',
                            '1B (Bahasa Melayu).',
                            '1C+ (Sejarah).',
                            '1C (Physics).',
                            '3D (Additional Mathematics, Chemistry, Biology).'
                        ]
                    }
                ]
            }
        ])
        
        return {
            EmailLink,
            SocialLink,
            Introduction,
            ExpertiseAreas,
            Experience,
            Education,
            ResumeLink
        }
    }
}
</script>
