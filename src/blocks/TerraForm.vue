<template>
	<section class="terra-form">
		<div class="terra-form__content">
			<div class="terra-form__content--header">
				<h2>День открытых дверей</h2>
				<div class="details">
					<h3>КУРСА DATA-SCIENCE И НЕЙРОННЫЕ СЕТИ</h3>
					<p>
						<span><b>29</b> ноября</span>
						<span><b>19:00</b> по МСК</span>
					</p>
				</div>
			</div>
			<p>Оставить заявку</p>
			<Quiz />
		</div>
	</section>
</template>

<script>
import Quiz from '../components/Quiz.vue'

export default {
	name: 'TerraForm',
	components: {
		Quiz
	}
}
</script>

<style lang="scss" scoped>
.terra-form {
	background: no-repeat url('../assets/bg.webp');
	background-size: cover;
	background-position: center;
	padding: 145px 0;
	&__content {
		max-width: 770px;
		padding: 60px 85px;
		background: #1B2B3A;
		border-radius: 8px;
		&--header {
			margin-bottom: 50px;
			display: flex;
			gap: 50px;
			h2 {
				font-size: 65px;
				color: #fff;
				font-weight: 400;
				line-height: 1.05em;
				flex: 1 0 250px;
			}
			.details {
				color: #A7BED3;
				font-size: 25px;
				padding-top: 10px;
				flex: 1 0 250px;
				h3 {
					font-weight: 400;
					font-size: inherit;
					margin-bottom: 39px;
					line-height: 28px;
				}
				b {
					color: #FF8B60;
					font-size: 35px;
				}
				p {
					display: flex;
					flex-direction: column;
				}
			}
		}
		> p {
			margin-bottom: 27px;
			font-size: 25px;
			color: #65B9F4;
		}
	}
}

@media (max-width: 860px) {
	.terra-form {
		&__content {
			padding: 60px 44px;
			max-width: 668px;
			&--header {
				gap: 60px;
			}
			> p {
				padding-left: 40px;
			}
			h2 {
				font-size: 50px;
			}
		}
	}
}

@media (max-width: 550px) {
	.terra-form {
		&__content {
			padding: 60px 10px;
			max-width: 668px;
			&--header {
				display: block;
				.details {
					margin-top: 35px;
					font-size: 20px;
					b {
						font-size: 30px;
					}
					p {
						flex-direction: row;
						justify-content: space-evenly;
					}
				}
			}
			> p {
				padding-left: 40px;
			}
			h2 {
				font-size: 50px;
			}
		}
	}
}
</style>