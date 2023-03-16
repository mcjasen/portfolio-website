<template>
    <header id="header">
        <div>
            <h1>Hi, my name is</h1>
        </div>
        <div>
            <h2>André Froning.</h2>
        </div>
        <h3 id="description">I'm a software engineer from Mainz, DE.</h3>
        <div>
            <a href="mailto:a.froning@aol.com?subject=Get%20in%20Touch" class="retro-btn">Get in Touch</a>
        </div>
    </header>
</template>

<!-- ----- ----- ----- ----- ----- ----- ----- VUE SCRIPT CONFIGURATION ----- ----- ----- ----- ----- ----- ----- -->

<script>
export default {
    name: "TheHeader"
}
</script>

<!-- ----- ----- ----- ----- ----- ----- ----- STYLESHEET CONFIGURATION ----- ----- ----- ----- ----- ----- ----- -->

<style lang="scss">
header {

    div{
        width: fit-content;
    }

    h1 {
        font-family: var(--font-code);
        font-size: var(--size-lg);
        color: var(--accent-color);
        margin-bottom: 10px;

        width: fit-content;     
        overflow: hidden;
        border-right: .15em solid transparent;
        white-space: nowrap;
        animation:
            typing2 .8s steps(100, end) forwards,
            blink-caret .5s 2;
    }

    h2 {
        font-family: var(--font-mark);
        font-size: clamp(40px, 8vw, 80px);
        color: var(--font-color-normal);
        margin-bottom: 20px;

        width: 0;
        display: inline-block;
        overflow: hidden;
        border-right: .15em solid transparent;
        white-space: nowrap;
        animation:
            typing2 2s forwards,
            blink-caret .5s 5;
        animation-delay: 1.2s;
    }

    /* The typing effect */
    @keyframes typing {
        from { max-width: 0;}
        to { max-width: 100%;}
    }

    @keyframes typing2 {
        from { width: 0 }
        to { width: 100% }
    }

    /* The typewriter cursor effect */
    @keyframes blink-caret {
        0% { border-color: transparent}
        100% {border-color: white}
    }

    h3 {
        font-family: var(--font-mark);
        font-size: clamp(40px, 8vw, 80px);
        margin-bottom: 60px;
        color: var(--font-color-accent);
        opacity: 0;

        animation: blend 2s forwards;
        animation-delay: 3.5s;
    }

    .retro-btn{
        opacity: 0;
        animation: blend 2s forwards;
        animation-delay: 3.5s;
    }

    @keyframes blend {
        from{opacity: 0;}
        to{opacity: 1;}        
    }

    .text-area {
        display: grid;
        grid-template-columns: 75% 25%;

        p {
            grid-column-start: 1;
            grid-column-end: 2;
            margin-bottom: 60px;
            text-align: justify;
        }
    }
}

@media (min-width: 765px) {
    header .text-area {
        grid-template-columns: 75% 25%;
    }
}

@media (max-width: 764px) {
    header .text-area {
        grid-template-columns: 100%;
    }
}

@media (max-height: 610px) {
    header {
        padding: 80px 0;
    }
}
</style>