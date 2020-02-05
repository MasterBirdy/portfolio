<template>
    <div id="skillsTab">
        <div class="title anim invisible">
            <a href="http://www.github.com/masterbirdy" target="_blank">
                <img
                    class="github"
                    src="../assets/images/github.svg"
                    alt="GitHub Icon"
                />
            </a>
            <h1 class="skills">Skills</h1>
            <a
                href="https://www.linkedin.com/in/matthew-ito-16a656137/"
                target="_blank"
            >
                <img
                    class="linkedin"
                    src="../assets/images/linkedin.svg"
                    alt="Linkedin Icon"
                />
            </a>
        </div>
        <div class="grid-list container anim invisible">
            <div class="grid-item">
                <ul class="list languages">
                    <li>HTML</li>
                    <li class="topic">CSS / CSS Preprocessors</li>
                    <ul>
                        <li>SASS</li>
                    </ul>
                    <li>Javascript</li>
                    <li>Front-end Frameworks</li>
                    <ul>
                        <li>Vue</li>
                        <ul>
                            <li>VueX</li>
                            <li>Nuxt.js</li>
                        </ul>
                    </ul>
                </ul>
            </div>
            <div class="grid-item">
                <ul class="technologies">
                    <li class="topic">Version Control</li>
                    <ul>
                        <li>Git</li>
                    </ul>
                    <li class="topic">Module Bundler</li>
                    <ul>
                        <li>Webpack</li>
                    </ul>
                    <li class="topic">Testing Frameworks</li>
                    <ul>
                        <li>Jasmine</li>
                    </ul>
                    <li>Responsive Design</li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
export default {};
</script>

<style scoped>
.title {
    position: relative;
    padding-top: 1.5rem;
    display: flex;
    width: 100%;
    justify-content: center;
    align-items: center;
}

.github {
    color: #181717;
    margin-right: 2rem;
}

.linkedin {
    filter: invert(29%) sepia(93%) saturate(1450%) hue-rotate(177deg)
        brightness(90%) contrast(101%);
    margin-left: 2rem;
}
h1 {
    color: black;
    font-family: "Montserrat", sans-serif;
    font-size: 4.25rem;
}

h2 {
    color: black;
    font-family: "Montserrat", sans-serif;
    font-size: 2.6rem;
    text-align: left;
}

img {
    height: 80px;
}

div.grid-list.container {
    display: flex;
    justify-content: space-between;
    margin-top: 1.5rem;
    max-width: 850px;
    transform: translateX(2.5rem);
}

.grid-item {
    text-align: left;
}

.less {
    font-weight: 600;
}

div.grid-list.container ul {
    text-align: left;
    display: inline-block;
    font-family: "Montserrat", sans-serif;
    font-weight: 600;
    font-size: 2rem;
}

.list {
    margin-left: 1.75rem;
}

ul li {
    margin-top: 0.6rem;
    margin-bottom: 0.6rem;
}

.topic {
    margin-bottom: 0.4rem;
}

ul ul {
    margin: 0 0 0 2rem;
}

ul ul li {
    font-size: 1.75rem;
    font-weight: 400;
    margin-top: 0.5rem;
    margin-bottom: 0.5rem;
}

ul ul li:first-child {
    margin-top: 0;
}

ul ul li:last-child {
    margin-bottom: 0;
}

@media screen and (max-width: 1024px) {
    div.grid-list.container {
        flex-direction: column;
        transform: translateX(0);
        padding-left: 2rem;
        margin-top: 0;
    }

    .languages,
    .linkedin,
    .github {
        margin: 0;
    }

    h1 {
        font-size: 3.25rem;
    }

    img {
        height: 3.25rem;
    }
    li,
    ul li,
    ul ul li {
        font-size: 2rem;
    }

    ul li {
        margin-top: 1rem;
        margin-bottom: 1rem;
    }

    ul ul li {
        margin-top: 1rem;
        margin-bottom: 1rem;
    }

    ul ul li:first-child {
        margin-top: 0.5rem;
    }
}

@media screen and (max-width: 767px) {
    h1 {
        font-size: 2.5rem;
        margin: 0;
    }

    img {
        height: 2.5rem;
    }

    li,
    ul li,
    ul ul li {
        font-size: 1.3rem;
    }

    .topic {
        margin-bottom: 0rem;
    }

    ul li {
        margin-top: 0.6rem;
        margin-bottom: 0.6rem;
    }

    ul ul li {
        margin-top: 0.5rem;
        margin-bottom: 0.5rem;
    }

    ul ul li:first-child {
        margin-top: 0rem;
    }
}
</style>
