<template>

    
    <div class="articleBloque">
        <img :src="`${lienImage}`"/>
        <h3>{{titre}}</h3>
        <p>{{date}}</p>  écrit par <p>{{auteur}}</p>
        <p> {{description}}</p>
        <a :href="`${lienArticle}`">Lien vers l'article</a>
    </div>
    
</template>

<script>
export default {

    // props propriétés paramétrées et gérées de l'extérieur du composant
    props: {
        source: String,
        auteur: String,
        titre: String,
        description: String,
        lienArticle: String,
        lienImage: String,
        date: String,
        contenu: String,

    }

}
</script>

<style >

.articleBloque {
    width: 200px;
}

img {
    width: 200px;
}
</style>
