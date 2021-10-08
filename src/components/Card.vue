<template>
  <div class="card">
      <div class="image">
          <img :src="`https://image.tmdb.org/t/p/w342${details.poster_path}`">
      </div>
    <div class="details-movie">
        <h3> <span>Titolo:</span> {{details.title ? details.title : details.name}}</h3>
        <h4> <span>Titolo originale:</span> {{details.original_title || details.original_name}}</h4>
        <div>
            <img v-if="flags.includes(details.original_language)" width="30" :src="require(`../assets/img/${details.original_language}.png`)">
            <img v-else :src="require(`../assets/img/pace.png`)"  width="30">
        </div>
        <div class="stars-vote">
            <h3> <span>Voto:</span></h3>
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
    width: 21.375rem;
    border: 1px solid #fff;
    height: 32.25rem;
    margin-bottom: .9375rem;

    
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
    height: 32.25rem;
    
}
.card:hover .details-movie{
    opacity: 1;
}
h3 span, h4 span{
    font-size: 1.25rem;
    font-weight: 600;
}
image{
    height: 32.25rem;
    width: 21.375rem;
    img{
        width: 100%;
        height: 100%;
        object-fit: contain;
    }
}
.overview{
    font-size: .8125rem;
}
.fa-star{
    color: yellow;
}
        

</style>