<template>
	<section class="reviews" ref="elem">
		<div class="reviews__header">
			<h2>Отзывы</h2>
			<figure>
				<iframe width="100%" src="https://www.youtube.com/embed/yMZQyyaZhRk" title="YouTube video player" frameborder="0" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
				<figcaption>У нас есть десятки отзывов и интервью, мы собрали для вас короткую версию буквально на 90 секунд</figcaption>
			</figure>
		</div>
		<div class="reviews__content">
			<h3>Еще отзывы наших учеников</h3>
			<figure v-for="(video, idx) in reviews.video" :key="idx">
				<iframe width="100%" :src="video.src" title="YouTube video player" frameborder="0" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
				<figcaption><b>{{ video.name }}</b><span>{{ video.time }}</span></figcaption>
			</figure>
		</div>
		<div class="text-reviews">
			<h3>О нас в отзовиках</h3>
			<div class="text-reviews__list" :style="{ transform: `translateX(${shiftText}px)` }" @wheel.prevent="wheelText">
				<figure v-for="(item, idx) in reviews.text" :key="idx" :class="{ opacity: idx !== selectedText }">
						<button type="button" class="prev" aria-label="Предыдущий" @click="selectedText--" :disabled="selectedText <= 0"></button>
						<button type="button" class="next" aria-label="Следующий" @click="selectedText++" :disabled="selectedText >= reviews.text.length - 1"></button>
					<a :href="item.href" tabindex="-1"><img :src="item.src"></a>
					<figcaption v-show="idx === selectedText"><a :href="item.href">Читать весь отзыв в отзовике</a></figcaption>
				</figure>
			</div>
		</div>
		<div class="social">
			<h3>О нас в соц.сетях</h3>
			<div class="social__list" :style="{ transform: `translateX(${shiftSocial}px)` }" @wheel.prevent="wheelSocial">
				<figure v-for="(item, idx) in reviews.social" :key="idx" :class="{ opacity: idx !== selectedSocial }">
					<template v-if="idx === selectedSocial">
						<button type="button" class="prev" aria-label="Предыдущий" @click="selectedSocial--" :disabled="selectedSocial <= 0"></button>
						<button type="button" class="next" aria-label="Следующий" @click="selectedSocial++" :disabled="selectedSocial >= reviews.social.length - 1"></button>
					</template>
					<a :href="item.href" tabindex="-1"><img :src="item.src"></a>
					<figcaption v-show="idx === selectedSocial"><a :href="item.href">Читать отзыв в соц.сети</a></figcaption>
				</figure>
			</div>
		</div>
	</section>
</template>

<script>
import reviews from '../assets/reviews'

export default {
	name: 'Reviews',
	data: () => ({
		reviews,
		selectedText: 0,
		selectedSocial: 0,
		shiftValue: 780
	}),
	computed: {
		shiftText() {
			return this.selectedText * -this.shiftValue
		},
		shiftSocial() {
			return this.selectedSocial * -this.shiftValue
		}
	},
	methods: {
		wheelText(e) {
			if (e.wheelDelta < 0) return this.selectedText++
			this.selectedText--
		},
		wheelSocial(e) {
			if (e.wheelDelta < 0) return this.selectedSocial++
			this.selectedSocial--
		}
	},
	watch: {
		selectedText(newVal, oldVal) {
			if (newVal < 0 || newVal > (this.reviews.text.length - 1)) {
				this.selectedText = oldVal
			}
		},
		selectedSocial(newVal, oldVal) {
			if (newVal < 0 || newVal > (this.reviews.social.length - 1)) {
				this.selectedSocial = oldVal
			}
		}
	},
	mounted() {
		if (this.$refs.elem.offsetWidth <= 768) return this.shiftValue = 320
	}
}
</script>

<style lang="scss" scoped>
.reviews {
	background: #FFFFFF;
	padding: 150px 0 0;
	h2 {
		font-size: 50px;
		line-height: 1.16em;
		font-weight: 400;
		padding-bottom: 50px;
	}
	iframe {
		aspect-ratio: 16 / 9;
	}
	&__header {
		padding: 0;
		display: flex;
		flex-wrap: wrap;
		> * {
			flex: 1 1 450px;
		}
		figcaption {
			font-family: 'Inter', sans-serif;
			font-size: 20px;
			line-height: 1.4em;
			color: #383838;
			margin-top: 30px;
		}
	}
	h3 {
		color: #3F5168;
		font-size: 50px;
		line-height: 1.16em;
		font-weight: 400;
		flex: 1 0 100%;
		margin-bottom: 50px;
	}
	&__content {
		padding: 0;
		display: flex;
		flex-wrap: wrap;
		justify-content: center;
		margin-top: 150px;
		gap: 49px;
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
				font-size: 16px;
			}
		}
	}
	.text-reviews, .social {
		padding-bottom: 0;
		&__list {
			display: flex;
			width: fit-content;
			transition-duration: 500ms;
			.opacity {
				opacity: .5;
				button {
					display: none;
				}
			}
			figure {
				padding: 30px 48px 50px;
				transform: translateX(25%);
				position: relative;
				width: 780px;
				button {
					position: absolute;
					top: 158px;
					width: 44px;
					height: 44px;
					border: none;
					background: none;
					cursor: pointer;
					z-index: 2;
				}
				.prev {
					background: no-repeat center url('../assets/arrow.svg');
					left: -10px;
					transform: rotateY(180deg);
					&:disabled {
						background: no-repeat center url('../assets/arrow-disabled.svg');
						transform: rotateY(0);
					}
				}
				.next {
					background: no-repeat center url('../assets/arrow.svg');
					right: -10px;
					&:disabled {
						background: no-repeat center url('../assets/arrow-disabled.svg');
						transform: rotateY(180deg);
					}
				}
				> a {
					box-shadow: 0px 4px 8px rgba(30, 35, 39, 0.1);
					display: flex;
					height: 300px;
				}
				img {
					display: block;
					margin: auto;
				}
				figcaption {
					font-size: 20px;
					margin-top: 25px;
					text-align: right;
					a {
						color: #FF8B60;
						text-decoration: none;
						&:focus {
							outline: 1px solid blue;
						}
					}
				}
			}
		}
	}
}

@media (max-width: 1240px) {
	.reviews {
		padding: 0 0 100px;
		h2, h3 {
			font-size: 40px;
		}
		> * {
			padding: 150px 20px 0 40px;
		}
		&__header {
			figcaption {
				margin-top: 15px;
				font-size: 18px;
			}
		}
		&__content {
			margin: 0;
			gap: 20px;
			justify-content: space-evenly;
			figure {
				flex-basis: 297px;
			}
		}
		.text-reviews, .social {
			padding: 150px 40px 0;
			&__list {
				figure {
					transform: translateX(calc(12.5% - 40px));
				}
			}
		}
	}
}

@media (max-width: 860px) {
	.reviews {
		h2, h3 {
			font-size: 30px;
		}
		.text-reviews, .social {
			&__list {
				figure {
					width: 320px;
					padding: 13px 19px 43px;
					transform: translateX(50%);
					.prev {
						left: 47%;
						transform: rotateY(180deg) translateX(100%);
						&:disabled {
							transform: rotateY(0) translateX(-100%);
						}
					}
					.next {
						right: 47%;
						transform: rotateY(0) translateX(100%);
						&:disabled {
							transform: rotateY(180deg) translateX(-100%);
						}
					}
					button {
						top: 85%;
					}
					figcaption {
						font-size: 14px;
						margin-top: 10px;
					}
					img {
						height: 100%;
					}
					> a {
						height: 130px;
					}
				}
			}
		}
	}
}

@media (max-width: 550px) {
	.reviews {
		> * {
			padding: 100px 10px 0;
		}
		&__header {
			figcaption {
				font-size: 14px;
			}
		}
		.text-reviews, .social {
			padding: 100px 10px 0;
			&__list {
				figure {
					transform: translateX(-10px);
				}
			}
		}
	}
}
</style>