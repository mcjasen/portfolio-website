<template>
    <div class="sliders">
        <div class="slider-left">
            <ul>
                <li>
                    <a href="https://www.github.com/mcjasen" target="_blank">
                        <svg role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>GitHub</title><path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"/></svg>
                    </a>
                </li>
                <li>
                    <a href="https://www.linkedin.com/in/andré-froning-3904a012b" target="_blank">
                        <svg role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>LinkedIn</title>
                            <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
                        </svg>
                    </a>
                </li>
                <li>
                    <a href="https://www.xing.com/profile/Andre_Froning/" target="_blank">
                        <svg role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>Xing</title>
                                <path d="M1.805 5.984l3.635 6.479L0 22.018h6.491l5.4-9.555-3.634-6.48H1.805z"></path>
                                <path d="M21.122 0l-10.49 18.642L17.396 31h6.582l-6.88-12.358L27.6 0h-6.478z"></path>
                        </svg>
                    </a>
                </li>
            </ul>
            <div class="slider-space"></div>
        </div>
        <div class="slider-right">
            <a href="mailto:a.froning@aol.com" class="slider-mail">a.froning@aol.com</a>
            <div class="slider-space"></div>
        </div>
    </div>
</template>

<!-- ----- ----- ----- ----- ----- ----- ----- VUE SCRIPT CONFIGURATION ----- ----- ----- ----- ----- ----- ----- -->

<script>
export default {
    name: 'TheSliders',
}
</script>

<!-- ----- ----- ----- ----- ----- ----- ----- STYLESHEET CONFIGURATION ----- ----- ----- ----- ----- ----- ----- -->

<style lang="scss">
.sliders {
    .slider-left {
        transform: translateX(-50%);

        ul {
            list-style-type: none;

            li {
                margin-top: 10px;
                height: 30px;
                width: 30px;

                a {
                    svg {
                        transition: all 0.4s ease-in-out;
                        fill: var(--font-color-normal);
                        margin: 10px 5px;
                    }

                    svg:hover {
                        transition: all 0.4s ease-in-out;
                        fill: var(--accent-color);
                        margin: 5px 5px 15px 5px;
                    }
                }
            }
        }
    }

    .slider-right {
        transform: translateX(50%);

        .slider-mail {
            transition: all 0.5s;
            writing-mode: vertical-lr;
            color: var(--font-color-normal);
        }

        .slider-mail:hover {
            transition: all 0.5s;
            color: var(--accent-color);
        }
    }
}

@media (min-width: 1041px) {
    .slider-left {
        left: 50px;
    }

    .slider-right {
        right: 50px;
    }
}

@media (max-width: 1080px) {
    .slider-left {
        left: 45px;
    }

    .slider-right {
        right: 45px;
    }
}

@media (max-width: 956px) {
    .slider-left {
        left: 40px;
    }

    .slider-right {
        right: 40px;
    }
}

@media (min-width: 769px) {
    .slider-left, .slider-right {
        position: fixed;
        bottom: 0;

        display: flex;
        flex-direction: column;
        align-items: center;

        .slider-space {
            background-color: var(--font-color-normal);
            margin-top: 10px;
            width: 1px;
            height: 120px;

        }
    }
}

@media (max-width: 768px) {
    .slider-left, .slider-right {
        display: none;
    }
}

@media (max-height: 400px) {
    .sliders {
        display: none;
    }
}
</style>