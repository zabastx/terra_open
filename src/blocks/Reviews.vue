<template>
	<section class="reviews">
		<div class="reviews__header">
			<h2>Отзывы</h2>
			<figure>
				<iframe width="100%" src="https://www.youtube.com/embed/yMZQyyaZhRk" title="YouTube video player" frameborder="0" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
				<figcaption>У нас есть десятки отзывов и интервью, мы собрали для вас короткую версию буквально на 90 секунд</figcaption>
			</figure>
		</div>
		<div class="reviews__content">
			<h2>Еще отзывы наших учеников</h2>
			<figure v-for="(review, idx) in reviews" :key="idx">
				<iframe width="100%" :src="review.src" title="YouTube video player" frameborder="0" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
				<figcaption><b>{{ review.name }}</b><span>{{ review.time }}</span></figcaption>
			</figure>
		</div>
	</section>
</template>

<script>
import reviews from '../assets/reviews'

export default {
	name: 'Reviews',
	data: () => ({
		reviews: reviews.list
	})
}
</script>

<style lang="scss" scoped>
.reviews {
	background: #FFFFFF;
	padding: 100px 0;
	h2 {
		font-size: 50px;
		line-height: 58px;
		font-weight: 400;
	}
	iframe {
		aspect-ratio: 16 / 9;
	}
	&__header {
		padding: 0;
		display: flex;
		flex-wrap: wrap;
		> * {
			flex: 1 0 450px;
		}
		figcaption {
			font-family: 'Inter', sans-serif;
			font-size: 20px;
			line-height: 28px;
			color: #383838;
			margin-top: 30px;
		}
	}
	&__content {
		padding: 0;
		display: flex;
		flex-wrap: wrap;
		justify-content: center;
		margin-top: 150px;
		gap: 49px;
		h2 {
			color: #3F5168;
			flex: 1 0 100%;
			margin-bottom: 50px;
		}
		figure {
			flex: 0 1 367px;
		}
		figcaption {
			display: flex;
			justify-content: space-between;
			margin-top: 10px;
			b {
				color: #FF8B60;
			}
			span {
				color: #4B6884;
			}
		}
	}
}
</style>