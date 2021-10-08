<template>
	<header>
        <nav>
            <div class="logo">BOOLFLIX</div>
            <form>
                <input type="text" v-model="searchText">
                <button type="submit" @click.prevent="$emit('searching', searchText)">Cerca</button>
            </form>
        </nav>
		
	</header>
</template>

<script>
export default {
	name: "Header",
	data() {
		return {
			searchText: ""
		}
	}
}
</script>

<style lang="scss" scoped>
header{
    padding: .9375rem;
    background-color: #000;
    nav{
        display: flex;
        justify-content: space-between;
        align-items: center;
        .logo{
            color: red;
            font-size: 1.875rem;
            font-weight: 600;
        }
    }
}
</style>
