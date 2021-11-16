<template>

<div class="articleContainer">
  // Affichage des éléments du tableau
  <Article v-for="(element, index) in news"
      :key="index"
    :lienImage= "element.urlToImage"
    :titre = "element.title"
    :date = "element.publishedAt"
    :auteur = "element.author"
    :description= "element.description"
    :lienArticle= "element.url"
  />
</div>
</template>

<script>
// Importation du component
import Article from "../components/Article.vue";

export default {
  // Appel du composant
  components:{

    Article: Article,
  },

  data () {
    return {
news: [],
    }
  },
// Requête asynchrone au montage de l'app
async mounted () {

      const url = "https://newsapi.org/v2/top-headlines?country=fr&apiKey=6221de66e11f403c8971008c84a197c5";

      // création de la const de réponse qui va chercher les options de l'API
      const response = await fetch(url);
      // Création de la const data qui nous permet la récupération des data stockées dans l'API
      const data = await response.json();

      // Récupération des datas dans un array
      this.news = data.articles
}

}
</script>

<style>
.articleContainer {
    display: flex;
    flex-direction: row;

}

</style>