<template>
    <label>Catégorie de News : </label>
    <input type="text" v-model="inputChoix" @keyup="getTypeSelect">
    // Affichage des éléments du tableau
    <Article v-for="(element, index) in generalNews"
    :key="index"
    :lienImage= "element.urlToImage"
    :titre = "element.title"
    :date = "element.publishedAt"
    :auteur = "element.author"
    :description= "element.description"
    :lienArticle= "element.url"/>
</template>

<script>
// Importation du component Article
import Article from "../components/Article.vue";

export default {
    // Data Properties
    data () {
        return {

            inputChoix: "",
            generalNews: [],
        }

    },
    // Appel du composant
    components:{
        Article: Article,
    },

methods: {
    // Methode asynchrone
    async getTypeSelect () {

        // Récupération de la valeur de l'input dans une constante
        const choixClient = this.inputChoix
        const url = `https://newsapi.org/v2/everything?q=${choixClient}&apiKey=6221de66e11f403c8971008c84a197c5`

        // création de la const de réponse qui va chercher les options de l'API
        const response = await fetch(url);
        // Création de la const data qui nous permet la récupération des data stockées dans l'API
        const data = await response.json();

        // Stockage des articles dans un array
        this.generalNews = data.articles
    }
}
}
</script>

<style scoped>

</style>