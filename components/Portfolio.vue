<template>
    <div id="portfolioTab" class="top container anim invisible">
        <h1 class="portfolioText">Portfolio</h1>
        <div class="grid">
            <portfolio-item
                v-for="(item, index) in portfolioItems"
                :key="item + index"
                :aTitle="item.title"
                :aContent="item.content"
                :demoLink="item.demoLink"
                :codeLink="item.codeLink"
                :class="[
                    index % 2 === 0 ? 'left-portfolio' : 'right-portfolio'
                ]"
            ></portfolio-item>
        </div>
    </div>
</template>

<script>
import PortfolioItem from "@/components/PortfolioItem";

export default {
    components: {
        PortfolioItem
    },
    data() {
        return {
            portfolioItems: [
                {
                    title: "Cat Blog",
                    content:
                        "Blog created by Nuxt.js framework for Vue as a static page generator for content dynamically created by Netlify CMS",
                    demoLink: "https://objective-dijkstra-75b79d.netlify.com/",
                    codeLink: "https://github.com/MasterBirdy/crispy-eureka"
                },
                {
                    title: "Country Flag Search",
                    content:
                        "Front End Mentor challenge replicating a UI design using a REST Countries API and Vue framework",
                    demoLink: "https://awesome-colden-14cbac.netlify.com/",
                    codeLink: "https://github.com/MasterBirdy/rest-countries"
                },
                {
                    title: "Weather App",
                    content:
                        "App using REST APIs to pull up weather data and display a stock image related to the data",
                    demoLink: "https://peaceful-saha-d013fd.netlify.com/",
                    codeLink: "https://github.com/MasterBirdy/weatherapp"
                },
                {
                    title: "API Shortener",
                    content:
                        "Front End Mentor challenge replicating a UI design using the Shortly URL Shortener",
                    demoLink: "https://masterbirdy.github.io/api-shortener/",
                    codeLink: "https://github.com/MasterBirdy/api-shortener"
                }
            ]
        };
    }
};
</script>

<style scoped>
.top {
    padding-top: 1.5rem;
}
h1 {
    font-family: "Montserrat", sans-serif;
    font-size: 4.25rem;
}

.grid {
    display: grid;
    margin-top: 2rem;
    grid-template-columns: 1fr 1fr;
    grid-row-gap: 1.5rem;
    grid-column-gap: 3rem;
    padding: 0rem 3.5rem;
}

@media screen and (max-width: 1024px) {
    .grid {
        grid-column-gap: 0;
        grid-row-gap: 1rem;
        padding: 0;
        grid-template-columns: 1fr;
    }

    h1 {
        font-size: 3.25rem;
    }
}

@media screen and (max-width: 767px) {
    h1 {
        font-size: 2.7rem;
    }
}
</style>
