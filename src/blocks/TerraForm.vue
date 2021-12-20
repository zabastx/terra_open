<template>
	<section class="terra-form">
		<div class="terra-form__content">
			<div class="terra-form__content--header">
				<h2>День открытых дверей</h2>
				<div class="details">
					<h3>КУРСА DATA-SCIENCE И НЕЙРОННЫЕ СЕТИ</h3>
					<p>
						<b>29</b> ноября<br>
						<b>19:00</b> по МСК
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
			flex-wrap: wrap;
			h2 {
				font-size: 65px;
				color: #fff;
				font-weight: 400;
				line-height: 68px;
				flex: 4 0 300px;
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
			}
		}
		> p {
			margin-bottom: 27px;
			font-size: 25px;
			color: #65B9F4;
		}
	}
}
</style>