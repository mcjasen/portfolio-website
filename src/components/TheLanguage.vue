<template>
    <a :href="link" target="_blank">
        <div class="language-element" :style="size">
            <img :src="file" 
                class="logo" 
                :alt="alt"
                @mouseover="setFocus()" 
                @mouseleave="unsetFocus()"
            >
            <div class="name" ref="name" :class="{visible: show}">{{ name }}</div>
        </div>
    </a>
</template>

<!-- ----- ----- ----- ----- ----- ----- ----- VUE SCRIPT CONFIGURATION ----- ----- ----- ----- ----- ----- ----- -->

<script>
export default {
    props: {
        name: {
            type: String,
            required: true
        },
        file: {
            type: String,
            required: true
        },
        alt: {
            required: true
        },
        link: {
            required: true
        },
        size: String,
    },
    name: 'TheLanguage',
    data(){
        return {
            show: false,
            max_width_icon: "60px"
        }
    },
    methods : {
        openNewTab(url){
            window.open(url, '_blank')
        },
        setFocus(){
            this.$refs.name.focus()
            this.show=true
        },
        unsetFocus(){
            this.$refs.name.blur()
            this.show=false
        }
    }
}
</script>

<!-- ----- ----- ----- ----- ----- ----- ----- STYLESHEET CONFIGURATION ----- ----- ----- ----- ----- ----- ----- -->

<style lang="scss">
.language-element{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin-left: 20px;

    img{
        height: auto;
        width: 60px;
        margin-bottom: 10px;
        transition: transform 0.25s ease-in-out;
    }

    img:hover,
    img:focus{
        transform: scale(1.1);
    }

    .name{
        text-align: center;
        color: var(--font-color-accent);
        font-family: var(--font-mark);
        transition: opacity 0.35s ease-in-out;
        opacity: 0;
    }

    .visible{
        opacity: 1;
    }

    /*.name:focus{
        opacity: 1;
    }*/

    /*.invisible{
        transition: opacity 0.25s ease-in;
        opacity: 0;
    }*/
}

@media (max-width: 500px){
    .language-element{
        margin-left: 10px;
    }
}

</style>