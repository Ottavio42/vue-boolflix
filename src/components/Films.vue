<template>
  <div class="container">
	<h2>I Film</h2>
	<ul>
		<li v-for="(film, index) in films" :key="index">
			<Card :details="film"/>
		</li>
	</ul>
	<h2>Le Serie Tv</h2>
	<ul>
		<li v-for="(serieTv, index) in serie" :key="index">
			<Card :details="serieTv"/>
		</li>
	</ul>
  </div>
</template>

<script>
import Card from './Card.vue';
export default {
	name: "Films",
	props: ['films', 'serie'],
	components: {
		Card
	}
}
</script>

<style lang="scss" scoped>
.container{
	background-color: #434343;
	padding: .9375rem;
	ul{
		display: flex;
		flex-wrap: wrap;
		list-style: none;
		justify-content: space-around;
	}
}
</style>