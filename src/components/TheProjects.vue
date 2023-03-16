<template>
    <section id="projects">
        <div class="section-header"><h1><span class="number">03.</span>Projects<span class="line"></span></h1></div>
        <div class="project-container">
            <Project
                subtitle="Master thesis, University of Applied Sciences, Trier"
                title="XR-CISE-Companion-App" 
                :description="{
                    'title': 'Android App to help conduct VR studies:',
                    'items': [
                        'collecting and storing sensor data to monitor the subject\'s health',
                        'asking study questions and sending messages to the subject who is wearing VR Glasses'
                    ]
                }" 
                link="https://gitlab.rlp.net/ndfr0541/xr-cise-companion-app"
                :technologies="[{
                        'name': 'Android Java',
                        'src': './logos/android.svg',
                        'alt': 'Android Logo',
                        'link': 'https://developer.android.com/'
                    }]"
                :pictures="[
                    {
                        'src':'./screenshots/XR-CISE-Companion-App 1.jpg'
                    }, 
                    {
                        'src':'./screenshots/XR-CISE-Companion-App 2.jpg'
                    }
                ]"
                :index="0"
            />
            <Project
                title="digital shopping list" 
                :description="{
                    'title': 'digital shopping list as a web-app:',
                    'items': [
                        'managing different lists with different items',
                        'automatically display photos matching a list or an article'
                    ]
                }" 
                link="https://github.com/mcjasen/digital-shopping-list"
                :technologies="[
                    {
                        'name': 'Vue.js',
                        'src': './logos/vue.svg',
                        'alt': 'Vue.js Logo',
                        'link': 'https://vuejs.org/'
                    },
                    {
                        'name': 'Spring',
                        'src': './logos/spring.svg',
                        'alt': 'Spring Logo',
                        'link': 'https://spring.io/'
                    },
                    {
                        'name': 'Docker',
                        'src': './logos/docker.svg',
                        'alt': 'Docker Logo',
                        'link': 'https://www.docker.com/'
                    },
                ]"
                :pictures="[
                    {
                        'src':'./screenshots/digital shopping list 1.png'
                    },
                    {
                        'src': './screenshots/digital shopping list 2.png'
                    }
                ]"
                :index="1"
            />
            <Project
                title="Notion Widget" 
                :description="{
                    'title': 'Android Widget for the productivity and note app, Notion:',
                    'items': [
                        'shows entries of a notion page as a list',
                        'list of entries can be grouped'
                    ]
                }" 
                link="https://github.com/mcjasen/notion-widget"
                :technologies="[{
                        'name': 'Android Java',
                        'src': './logos/android.svg',
                        'alt': 'Android Logo',
                        'link': 'https://developer.android.com/'
                    }]"
                :pictures="[
                    {
                        'src':'./screenshots/Notion Widget.jpg'
                    }
                ]"
                :index="2"
            />
            <Project
                subtitle="Bachelor thesis, Baden-Wuerttemberg Cooperative State University (DHBW), Mannheim"
                title="Control Screen" 
                :description="{
                    'title': 'Development of an individual SAP screen with Screen Personas:',
                    'items': [
                        'input of different search criteria',
                        'execution of various SAP functions, such as an ABC analysis'
                    ]
                }"
                :technologies="[{
                        'name': 'Java Script',
                        'src': './logos/javascript.png',
                        'alt': 'JavaScript Logo',
                        'link': 'https://www.javascript.com/',
                        'size' : 'width: 60px'
                    }]"
                :pictures="[
                    {
                        'src':'./screenshots/Control Screen.png',
                        'size' : 'width: 450px;'
                    }
                ]"
                :index="3"
            />
        </div>
    </section>
</template>

<!-- ----- ----- ----- ----- ----- ----- ----- VUE SCRIPT CONFIGURATION ----- ----- ----- ----- ----- ----- ----- -->

<script>
import Project from '@/components/TheProject';

export default {
    name: 'TheProjects',
    components: {
        Project
    },
}
</script>

<!-- ----- ----- ----- ----- ----- ----- ----- STYLESHEET CONFIGURATION ----- ----- ----- ----- ----- ----- ----- -->

<style lang="scss">

.project-container{
    margin-bottom: 10px;
}
</style>