<template>
    <div>
        <div class="project left" v-if="!isMobile() && index%2===0">
            <div class="text"> 
                <div class="subtitle">{{ subtitle }}</div>
                <div class="title">{{ title }}</div>
                <div class="description list">
                    <div>{{ description.title }}</div>
                    <ul v-if="description.items">
                        <li v-for="item in description.items" :key="item">{{ item }}</li>
                    </ul>
                </div>
                <div class="links-container">
                    <a class="project-link" :href="link" target="_blank" v-if="link">
                        <img src="../assets/logos/github.svg" alt="GitHub logo" title="open GitHub-Project">
                    </a>
                    <Language 
                        :class="{technology: index === 0}" 
                        v-for="(technology, index) in technologies" 
                        :key="technology"
                        :name="technology.name" 
                        :file="technology.src" 
                        :alt="technology.alt" 
                        :link="technology.link" 
                        :size="technology.size"
                    />
                </div>
            </div>
            <div class="screenshot-container">
                <img 
                    class="screenshot" 
                    v-for="picture in pictures" 
                    :key="picture" 
                    :src=picture.src 
                    :style="picture.size" 
                    @click="showScreenshot(picture)"
                    title="open full-screen"
                >
            </div>
        </div>

        <div class="project right" v-if="!isMobile() && index%2!==0">
            <div class="screenshot-container">
                <img 
                    class="screenshot" 
                    v-for="picture in pictures" 
                    :key="picture" 
                    :src=picture.src 
                    :style="picture.size" 
                    @click="showScreenshot(picture)"
                    title="open full-screen"
                >
            </div>
            <div class="text"> 
                <div class="subtitle">{{ subtitle }}</div>
                <div class="title">{{ title }}</div>
                <div class="description list">
                    <div>{{ description.title }}</div>
                    <ul v-if="description.items">
                        <li v-for="item in description.items" :key="item">{{ item }}</li>
                    </ul>
                </div>
                <div class="links-container">
                    <a class="project-link" :href="link" target="_blank" v-if="link">
                        <img src="../assets/logos/github.svg" alt="GitHub logo" title="open GitHub-Project">
                    </a>
                    <Language 
                        :class="{technology: index === 0}" 
                        v-for="(technology, index) in technologies" 
                        :key="technology"
                        :name="technology.name" 
                        :file="technology.src" 
                        :alt="technology.alt" 
                        :link="technology.link" 
                        :size="technology.size"
                    />
                </div>
            </div>
        </div>

        <div class="project mobile" v-if="isMobile()">
            <div class="text"> 
                <div class="subtitle">{{ subtitle }}</div>
                <div class="title">{{ title }}</div>
                <div class="description list">
                    <div>{{ description.title }}</div>
                    <ul v-if="description.items">
                        <li v-for="item in description.items" :key="item">{{ item }}</li>
                    </ul>
                </div>
                <div class="links-container">
                    <a class="project-link" :href="link" target="_blank" v-if="link">
                        <img src="../assets/logos/github.svg" alt="GitHub logo" title="open GitHub-Project">
                    </a>
                    <Language 
                        :class="{technology: index === 0}" 
                        v-for="(technology, index) in technologies" 
                        :key="technology"
                        :name="technology.name" 
                        :file="technology.src" 
                        :alt="technology.alt" 
                        :link="technology.link" 
                        :size="technology.size"
                    />
                </div>
            </div>
            <div class="screenshot-container">
                <img 
                    class="screenshot" 
                    :class="{screenshots: pictures.length > 1}"
                    v-for="picture in pictures" 
                    :key="picture" 
                    :src=picture.src 
                    :style="picture.size" 
                    @click="showScreenshot(picture)"
                    title="open full-screen"
                >
            </div>
        </div>
    </div>
</template>

<!-- ----- ----- ----- ----- ----- ----- ----- VUE SCRIPT CONFIGURATION ----- ----- ----- ----- ----- ----- ----- -->

<script>
import Language from '@/components/TheLanguage'

export default {
    props: {
        subtitle: {
            type: String,
        },
        title: {
            type: String,
            required: true
        },
        description: {
            type: Object,
            required: true
        },
        link: {
            type: String
        },
        technologies: {
            type: Array
        },
        pictures:{
            type: Array
        },
        index: {
            type: Number,
            required: true
        }
    },
    name: 'TheProject',
    components : {
        Language
    },
    methods:{
        showScreenshot(picture){
            window.open(picture.src, '_blank')
        },
        isMobile(){
            return screen.width < 1000
        }
    }
}
</script>

<!-- ----- ----- ----- ----- ----- ----- ----- STYLESHEET CONFIGURATION ----- ----- ----- ----- ----- ----- ----- -->

<style lang="scss">

.project{
    display: grid;
    align-items: center;
    margin-bottom: 120px;
}

.text{
    .subtitle{
        color: var(--accent-color);
        font-family: var(--font-text);
        font-size: var(--size-lg);
        margin-bottom: 20px;
    }

    .title{
        font-size: var(--headline-sm);
        font-family: var(--font-mark);
        margin-bottom: 20px;
    }
    
    .description{
        font-size: var(--size-lg);
        margin-bottom: 20px;
    }

    .links-container{
        display: flex;
        justify-content: space-between;

        .project-link{
            img{
                width: 55px;
                transition: transform 0.25s ease-in-out;
            }

            img:hover,
            img:focus{
                transform: scale(1.1);
            }
        }

        .technology{
            margin-left: auto;
        }
    }
}

.screenshot-container{
    margin-left: 20px;
    display: flex;
    justify-content: center;

    .screenshot{
        width: 215px;
        margin: 0 20px 0 0;
    }

    img{
        transition: transform 0.5s ease-in-out;
    }

    img:hover,
    img:focus{
        transform: scale(1.1);
    }
}

@media (max-width: 640px){
    .screenshot-container{
        .screenshot{
            max-width: 90%;
        }

        .screenshots{
            max-width: 45%;
        }
    }
}

.left{
    grid-template-columns: 1fr 1fr;
}

.right{
    grid-template-columns: 1fr 1fr;

    .screenshot-container{
        margin-left: 0px;
    }
}

.mobile{
    flex-direction: column;
}

</style>