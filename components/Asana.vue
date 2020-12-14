<template>
 <article class="asana">
	 <img :src="pose.img_url" :alt="pose.sanskrit_name" class="asana__img">
	 <h2 class="asana__title">{{ pose.sanskrit_name }}</h2>
	 <p class="asana__copy">{{ pose.english_name }}</p>
 </article>
</template>

<script>
export default {
	props: {
		pose: Object
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

