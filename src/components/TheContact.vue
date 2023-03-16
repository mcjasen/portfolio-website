<template>
    <section id="contact">
        <div class="section-header"><h1><span class="number">04.</span>Contact<span class="line"></span></h1></div>
        <div class="content">
            <div class="text">Do you like what I do?</div>
            <div class="text">Write me an email and we can get in touch</div>
            <div class="button">
                <a href="mailto:a.froning@aol.com" class="retro-btn">Write a Mail</a>
            </div>
        </div>
    </section>
</template>

<!-- ----- ----- ----- ----- ----- ----- ----- VUE SCRIPT CONFIGURATION ----- ----- ----- ----- ----- ----- ----- -->

<script>
export default {
    name: "TheContact"
}
</script>

<!-- ----- ----- ----- ----- ----- ----- ----- STYLESHEET CONFIGURATION ----- ----- ----- ----- ----- ----- ----- -->

<style lang="scss">
#contact {
    display: flex;
    flex-direction: column;

    .content{
        text-align: center;    
    
        .text{
            font-family: var(--font-mark);
            color: var(--font-color-accent);
            font-size: var(--size-xl);
            margin-bottom: 20px;
        }

        .button{
            margin-top: 60px;
        }

        a{
            width: auto;
            margin-top: 20px;
        }

    }
}
</style>