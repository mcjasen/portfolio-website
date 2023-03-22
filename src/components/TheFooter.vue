<template>
    <footer>
        <a href="https://github.com/mcjasen/portfolio-website" target="_blank">
            Designed by André Froning
        </a>
        <div> 
            Built by <a href="https://www.github.com/bchiang7/v4" target="_blank"> Brittany Chiang</a> & <a href="https://github.com/markuskooche/PortfolioWebpageV1" target="_blank"> Markus Koch </a>
        </div>
    </footer>
</template>

<!-- ----- ----- ----- ----- ----- ----- ----- VUE SCRIPT CONFIGURATION ----- ----- ----- ----- ----- ----- ----- -->

<script>
export default {
    name: 'TheFooter',
}
</script>

<!-- ----- ----- ----- ----- ----- ----- ----- STYLESHEET CONFIGURATION ----- ----- ----- ----- ----- ----- ----- -->

<style lang="scss">
footer {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-top: -70px;

    div {
        font-family: var(--font-code);
        font-size: var(--size-sm);
    }

    a {
        font-family: var(--font-code);
        font-size: var(--size-sm);

        transition: all 0.6s;
        color: var(--font-color-normal);

        margin-bottom: 8px;
    }

    a:hover {
        transition: all 0.6s;
        color: var(--accent-color);
    }
}
</style>
