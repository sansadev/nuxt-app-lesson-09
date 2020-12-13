<template>
 <article class="asana">
	 <img :src="asana.pos" :alt="asana.name" class="card__img">
	 <h2 class="card__title">{{ asana.name }}</h2>
	 <p class="card__copy">{{ asana.procedure }}</p>
 </article>
</template>

<script>
export default {
	props: {
		asana: Object
	}
}
</script>


<style lang="scss">
.asana {
	margin: 1rem;
	border: 1px solid #000;
	padding: 1.5rem;
	max-width: 200px;
	min-height: 200px;
	&__img {
		display: block;
		margin-bottom: 1rem;
	}
	&__title {
		font-size: 1rem;
		margin-bottom: .25rem;
	}
	&__copy {
		font-size: .875rem;
	}
}
</style>

