<template>
  <div class="card">
      <div class="image">
          <img :src="`https://image.tmdb.org/t/p/w342${details.poster_path}`">
      </div>
    <div class="details-movie">
        <h3>Titolo: {{details.title ? details.title : details.name}}</h3>
        <h4> Titolo Originale: {{details.original_title || details.original_name}}</h4>
        <div>
            <img v-if="flags.includes(details.original_language)" width="30" :src="require(`../assets/img/${details.original_language}.png`)">
            <img v-else :src="require(`../assets/img/pace.png`)"  width="30">
        </div>
        <div class="stars-vote">
            <h3>Voto:</h3>
            <div v-for="(star, index) in Math.floor(details.vote_average / 2)" :key="index" class="fas fa-star">
        </div>
        <p class="overview">
          {{ details.overview }}
        </p>
    </div>
    </div>
	
  </div>
</template>

<script>
import "@fortawesome/fontawesome-free/js/all.js";
export default {
	name: "Card",
	props: ['details'],
	data() {
		return {
			flags: ['it', 'en', 'fr']
		}
	}

}
</script>

<style lang="scss" scoped>
.card{
    position: relative;
    width: calc((100% / 5) - 20px);
    
}
.card .details-movie{
    opacity: 0;
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    height: 100%;
    background: #000;
    color: #fff;
    width: 342px;
    border:1px solid #fff;
    
}
.card:hover .details-movie{
    opacity: 1;

}
image{
    border: 1px solid #fff;
}
        

</style>