<template>
    <section id="about">
        <div class="about-container" :class="{mobile: isMobile()}">
            <div class="text">
                <div class="section-header"><h1><span class="number">01.</span>About Me<span class="line"></span></h1></div>
                <div v-if="isMobile()" class="image" :class="{'mobile-image': isMobile()}">
                    <img src="../assets/images/portrait.jpg" alt="personal portrait" class="portrait">
                </div>
                <p class="about-text about-space">Hey, I am André Froning, a software engineer from Mainz, DE. I studied computer science at the University of Applied Sciences in Trier.</p>
                <p class="about-text">Here are a few technologies I've been working with in recent projects:</p>
                <div class="language-container">
                    <Language name="Vue.js" file="./logos/vue.svg" alt="Vue.js Logo" link="https://vuejs.org/"/>
                    <Language name="Android Java" file="./logos/android.svg" alt="Android Logo" link="https://developer.android.com/"/>
                    <Language name="Spring" file="./logos/spring.svg" alt="Spring Logo" link="https://spring.io/"/>
                </div>
            </div>
            <div v-if="!isMobile()" class="image">
                <img src="../assets/images/portrait.jpg" alt="personal portrait" class="portrait">
            </div>
        </div>
    </section>
</template>

<!-- ----- ----- ----- ----- ----- ----- ----- VUE SCRIPT CONFIGURATION ----- ----- ----- ----- ----- ----- ----- -->

<script>
import Language from '@/components/TheLanguage'

export default {
    components:{
        Language
    },
    methods: {
        isMobile(){
            return screen.width < 700
        }
    }
}

</script>

<!-- ----- ----- ----- ----- ----- ----- ----- STYLESHEET CONFIGURATION ----- ----- ----- ----- ----- ----- ----- -->

<style lang="scss">
#about {
    .mobile{
        flex-direction: column;
    }

    .about-container {
        display: flex;
        align-items: center;

        .image{
            margin-top: -20px;
            margin-bottom: 20px;

            .portrait {
                border-radius: 50%;
                margin: 20px 60px;

                width: 190px;
                height: 190px;
            }
        }

        .mobile-image{
            display:flex;
            justify-content: center;
        }

        .about-text {
            font-size: 18px;
            margin-bottom: 6px;

            a {
                transition: 0.3s;
                text-decoration: underline;
                color: var(--font-color-accent);
            }

            a:hover {
                transition: 0.3s;
                color: var(--accent-color);
            }
        }

        .about-space {
            margin-bottom: 10px;
        }

        .language-container-mobile,
        .language-container {
            display: flex;
            align-items: flex-start;
            margin-top: 35px;
        }
    }
}
</style>