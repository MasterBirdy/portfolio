<template>
    <div class="item">
        <img src="../assets/images/computerhtml.svg" alt="Computer code" />
        <h1>{{ aTitle }}</h1>
        <p>{{ aContent }}</p>
        <div class="flex">
            <a :href="demoLink" target="_blank"
                ><button class="demo">demo</button></a
            >
            <a :href="codeLink" target="_blank"
                ><button class="code">code</button></a
            >
        </div>
    </div>
</template>

<script>
export default {
    props: {
        aTitle: {
            type: String,
            default: "",
            required: true
        },
        aContent: {
            type: String,
            default: "",
            required: true
        },
        demoLink: {
            type: String,
            default: "",
            required: true
        },
        codeLink: {
            type: String,
            default: "",
            required: true
        }
    }
};
</script>

<style scoped>
.item {
    border: 8px solid #ffb8c3;
    border-radius: 10px;
    padding: 1rem;
}

img {
    margin: -3.5rem 0 -3rem;
    height: 250px;
}

h1 {
    font-size: 2.75rem;
    font-weight: 600;
    font-family: "Montserrat", sans-serif;
    margin-bottom: 0.25rem;
}
p {
    font-family: "Source Sans Pro", sans-serif;
    color: white;
    font-size: 1.5rem;
    font-weight: 400;
}

.flex {
    display: flex;
    justify-content: center;
}

button {
    background-color: white;
    padding: 1rem 2.5rem;
    font-family: "Montserrat", sans-serif;
    font-size: 1.8rem;
    border: none;
    font-weight: 700;
    border-radius: 30px;
    cursor: pointer;
}

.demo {
    color: #da76b8;
    margin-right: 1rem;
}

.code {
    color: #dd8877;
}

@media screen and (max-width: 1024px) {
    h1 {
        font-size: 2.5rem;
    }

    p {
        font-size: 1.5rem;
    }
    button {
        font-size: 1.7rem;
        padding: 0.75rem 1.5rem;
    }

    .demo {
        margin-right: 0.5rem;
    }

    .flex {
        margin-top: 0.5rem;
        flex-direction: row;
    }
}

@media screen and (max-width: 767px) {
    h1 {
        font-size: 2.2rem;
    }

    p {
        font-size: 1.3rem;
    }

    button {
        font-size: 1.5rem;
    }
}
</style>
