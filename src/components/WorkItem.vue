<template>
    <div class="work">
        <div class="date">{{ date }}</div>
        <div class="element-box">
            <div class="title">{{ title }}</div>
            <a :href="link" target="_blank"> 
                <span class="company">{{ company }}</span> 
            </a>
            <div class="activities list" v-if="activities && activities.length > 0">
                <ul>
                    <li v-for="activity in activities" :key="activity">{{ activity }}</li>
                </ul>
            </div>
            <div class="activities" v-if="specialisation">{{ specialisation }}</div>
        </div>
    </div>
</template>

<script>
export default({
    props:{
        date: {
            type: String,
            required: true
        },
        title:{
            type: String,
            required: true
        },
        company: String,
        link: String,
        activities: {
            type: Array
        },
        specialisation: String
    }
})
</script>

<style lang="scss" scoped>
.date{
    color: var(--font-color-accent);
    font-family: var(--font-mark);
    font-size: var(--size-lg);
}

.element-box{
    margin-top: 10px;
    border: 1px solid var(--accent-color);
    border-radius: 8px;
    padding: 10px;
    display: flex;
    flex-direction: column;

    .title{
        font-family: var(--font-mark);
        font-size: var(--size-xl);
    }

    .company{
        font-family: var(--font-color-accent);
        font-size: var(--size-lg);
        color: var(--font-color-normal);
        /*display: inline-block;
        position: relative;*/

        background-image: linear-gradient(currentColor, currentColor);
        background-position: 50% 100%;
        background-repeat: no-repeat;
        background-size: 0% 2px;
        transition: background-size .4s;
    }

    .company:hover{
        background-size: 100% 2px;
    }



    /*.company::after{
        content: '';
        position: absolute;
        width: 100%;
        transform: scaleX(0);
        height: 2px;
        bottom: 0px;
        left: 0px;
        background-color: var(--font-color-accent);
        transform-origin: bottom right;
        transition: transform 0.25s ease-out;
    }

    .company:hover::after {
        transform: scaleX(1);
        transform-origin: bottom left;
    }*/

    .activities{
        font-family: var(--font-color-accent);
        font-size: var(--size-lg);
        color: var(--font-color-accent);
    }
}

.element-box > div, a{
    margin: 8px;
}
</style>
