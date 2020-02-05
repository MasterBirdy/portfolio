<template>
    <div id="contactTab" class="anim invisible">
        <h1 class="contact-title">Contact</h1>
        <p class="contact-text">
            Thanks for taking the time to visit! I am always interested in
            hearing about what kind of website you'd like to build! If you would
            like to work together, please send me an e-mail at
            <a href="mailto:hello@mattito.dev">hello@mattito.dev</a>!
        </p>
        <div class="handWave anim invisible">👋</div>
    </div>
</template>

<script>
export default {};
</script>

<style scoped>
#contactTab {
    position: relative;
    height: 100%;
    padding-top: 1rem;
}

h1 {
    font-size: 3.25rem;
    font-family: "Montserrat", sans-serif;
    font-weight: 700;
}

p {
    margin: 0 auto;
    padding: 0 2rem;
    margin-top: 0.5rem;
    font-family: "Source Sans Pro", sans-serif;
    color: white;
    font-size: 1.5rem;
    max-width: 800px;
    font-size: 1.5rem;
}

a {
    color: purple;
    font-weight: 700;
}

.handWave {
    display: inline-block;
    font-size: 5.5rem;
    margin-top: 1.5rem;
}

@media screen and (max-width: 767px) {
    h1 {
        font-size: 2.7rem;
    }

    p {
        font-size: 1.3rem;
    }
}
</style>
