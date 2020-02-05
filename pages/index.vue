<template>
    <div>
        <div class="blue">
            <nav class="container">
                <ul>
                    <li><a href="#skillsTab">skills</a></li>
                    <li><a href="#portfolioTab">portfolio</a></li>
                    <li><a href="#contactTab">contact</a></li>
                </ul>
            </nav>
            <div class="blue-container">
                <div class="flex container">
                    <div class="text anim">
                        <h1 class="header">Hello!</h1>
                        <h1 class="header">I'm Matthew.</h1>
                        <h2 class="header">Front-end web developer</h2>
                    </div>
                    <img
                        class="laptop-pic"
                        src="../assets/images/computer.svg"
                        alt="A blue laptop"
                    />
                </div>
            </div>
        </div>
        <div class="off-white">
            <skills></skills>
        </div>
        <div class="pink">
            <portfolio></portfolio>
        </div>
        <div class="light-blue">
            <contact></contact>
        </div>
    </div>
</template>

<script>
import gsap from "gsap";
import Skills from "@/components/Skills";
import Portfolio from "@/components/Portfolio";
import Contact from "@/components/Contact";

export default {
    components: {
        Skills,
        Portfolio,
        Contact
    },
    computed: {
        mobileSize() {
            return window.innerWidth < 1024;
        }
    },
    mounted() {
        const anims = Array.from(document.querySelectorAll(".anim"));
        const animations = [];
        const observer = new IntersectionObserver((entries) => {
            entries.forEach((entry) => {
                if (entry.intersectionRatio > 0) {
                    animations[anims.indexOf(entry.target)].play();
                }
            });
        });

        for (let i = 0; i < anims.length; i++) {
            if (i === 5) {
                animations[i] = gsap.timeline({ paused: true, repeat: -1 });
            } else {
                animations[i] = gsap.timeline({ paused: true });
            }
            observer.observe(anims[i]);
        }

        animations[0]
            .from(".header", {
                x: -150,
                duration: 1.5,
                opacity: 0,
                stagger: 0.5,
                ease: "power2.out"
            })
            .from(
                ".laptop-pic",
                {
                    x: this.mobileSize ? -150 : 150,
                    duration: 1.5,
                    opacity: 0,
                    delay: 1.5,
                    ease: "power2.out"
                },
                "-=3"
            )
            .from(
                "nav ul li",
                {
                    x: -150,
                    duration: 1.5,
                    opacity: 0,
                    stagger: 0.3,
                    ease: "power2.out"
                },
                "-=2.5"
            );
        animations[1]
            .from(".github", {
                x: this.mobileSize ? 0 : -150,
                delay: 0.3,
                duration: 1.5,
                opacity: 0,
                ease: "power2.out"
            })
            .from(
                ".linkedin",
                {
                    x: this.mobileSize ? 0 : 150,
                    duration: 1.5,
                    opacity: 0,
                    ease: "power2.out"
                },
                "-=1.5"
            )
            .from(
                ".skills",
                {
                    opacity: 0,
                    duration: 2.5,
                    ease: "power2.out"
                },
                "-=1.8"
            );
        animations[2]
            .from("ul.languages li", {
                x: -150,
                delay: 0.3,
                stagger: 0.1,
                duration: 1.5,
                opacity: 0,
                ease: "power2.out"
            })
            .from(
                "ul.technologies li",
                {
                    x: this.mobileSize ? -150 : 150,
                    duration: 1.5,
                    stagger: 0.1,
                    opacity: 0,
                    ease: "power2.out"
                },
                this.mobileSize ? "-=1.5" : "-=2.1"
            );
        animations[3]
            .from(".portfolioText", {
                x: -150,
                duration: 1.5,
                opacity: 0,
                ease: "power2.out"
            })
            .from(
                ".left-portfolio",
                {
                    x: -150,
                    duration: 1.5,
                    stagger: 0.3,
                    opacity: 0,
                    ease: "power2.out"
                },
                "-=1.1"
            )
            .from(
                ".right-portfolio",
                {
                    x: this.mobileSize ? -150 : 150,
                    duration: 1.5,
                    stagger: 0.3,
                    opacity: 0,
                    ease: "power2.out"
                },
                this.mobileSize ? "-=1.65" : "-=1.8"
            );
        animations[4]
            .from(".contact-title", {
                x: -150,
                duration: 1.5,
                opacity: 0,
                ease: "power2.out"
            })
            .from(
                ".contact-text",
                {
                    x: -150,
                    duration: 1.5,
                    opacity: 0,
                    ease: "power2.out"
                },
                "-=1.2"
            );
        animations[5]
            .to(".handWave", {
                rotation: 75,
                duration: 1.4,
                ease: "power2.out"
            })
            .to(".handWave", {
                rotation: 0,
                duration: 1.1,
                ease: "power1.out"
            });
    }
};
</script>

<style>
.blue {
    background-color: #5584fe;
}

a {
    text-decoration: none;
    color: white;
}

.blue-container {
    display: flex;
    width: 100%;
    height: 70vh;
    min-height: 600px;
    font-family: "Montserrat", sans-serif;
    justify-content: center;
}

.flex {
    display: flex;
    align-items: center;
    padding-top: 1rem;
}

.text {
    margin-right: 2rem;
    margin-bottom: 2rem;
    white-space: nowrap;
}

h1 {
    color: white;
    font-size: 4.875rem;
}

h2 {
    color: white;
    font-size: 3rem;
    font-family: "Source Sans Pro", sans-serif;
}

.container {
    max-width: 75rem;
    margin: 0 auto;
}

img.laptop-pic {
    height: 75%;
    max-height: 400px;
}

nav {
    margin-bottom: -1.5rem;
}

nav ul {
    list-style: none;
    font-family: "Montserrat", sans-serif;
    display: flex;
    justify-content: flex-end;
    padding-top: 1.5rem;
}

nav ul li {
    margin-right: 2.375rem;
    color: white;
    font-weight: 700;
    font-size: 1.75rem;
    white-space: nowrap;
}

.off-white {
    background-color: #f7f7f7;
    text-align: center;
    padding: 1rem;
    padding-bottom: 4rem;
    min-height: 60vh;
}

.pink {
    background-color: #ed95a3;
    text-align: center;
    padding: 1rem;
    padding-bottom: 4rem;
}

.light-blue {
    background-color: #8fbeea;
    text-align: center;
    padding: 1rem;
    padding-bottom: 4rem;
}

@media screen and (max-width: 1024px) {
    h1 {
        font-size: 3.25rem;
        margin-bottom: 0.5rem;
    }
    h2 {
        font-size: 2.25rem;
    }
    .container {
        width: 95%;
        margin: 0 auto;
    }

    .blue-container {
        flex-direction: column;
        min-height: 98vh;
    }

    .flex {
        flex-direction: column;
        padding-top: 0;
    }

    .text {
        white-space: normal;
    }

    .laptop-pic {
        height: 50%;
        max-height: 200px;
    }

    img {
        width: 100%;
    }

    nav {
        margin-bottom: 0;
        margin-right: 0;
        width: 100%;
    }

    nav ul {
        padding-top: 0.5rem;
        justify-content: space-around;
    }

    nav ul li {
        margin-right: 0;
        font-size: 2.1rem;
    }

    .text {
        margin-right: 0;
        margin-bottom: 0;
    }

    .light-blue {
        min-height: 50vh;
    }

    .off-white {
        min-height: 103vh;
    }
}

@media screen and (max-width: 1024px) and (orientation: landscape) {
    .flex {
        flex-direction: row;
        justify-content: center;
        padding-top: 0;
    }

    nav ul li {
        font-size: 1.5rem;
    }

    .laptop-pic {
        width: 50%;
    }
}

@media screen and (max-width: 767px) {
    h1 {
        font-size: 2.6rem;
    }
    h2 {
        font-size: 1.85rem;
    }
    nav ul li {
        font-size: 1.3rem;
    }
}
</style>
