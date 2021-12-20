<template>
	<section class="course">
		<div class="course__content">
			<div class="course__content--description">
				<h2>Курс “Data science и нейронные сети”</h2>
				<p>Вас ждут занятия, домашние задания, ответы на вопросы от кураторов и дипломный проект в конце обучения</p>
			</div>
			<div class="course__content--list">
				<div class="item">
					<h3>9 месяцев обучения</h3>
					<p class="text">Курс расчитан на 9 месяцев, за которые вы освоите новую профессию</p>
				</div>
				<div class="item">
					<h3>Поддержка кураторов</h3>
					<p class="text">Поддержка кураторов на протяжении всего времени обучения: <br>
						проверка домашних заданий за 1 день,<br>
						ответ кураторов в течение 10 минут,<br>
						до 60 zoom консультаций с куратором</p>
				</div>
				<div class="item">
					<h3>Гарантия трудоустройства по договору</h3>
					<p class="text">Гарантия прописана в договоре<br>Трудоустройство за 1 месяц<br>Лучших студентов нанимаем к себе в штат</p>
				</div>
				<div class="item">
					<h3>Созданный AI проект</h3>
					<p class="text">За время курса вы создадите собственный AI проект под руководством куратора. Мы сопроводим вас на всех этапах создания проекта</p>
				</div>
				<div class="item">
					<h3>Диплом/сертификат</h3>
					<p class="text">По итогу обучения вы получаете диплом/сертификат</p>
				</div>
			</div>
		</div>
	</section>
</template>

<script>
export default {
	name: 'Course'
}
</script>

<style lang="scss" scoped>
.course {
	background: #F6F6F6;
	color: #000;
	&__content {
		display: flex;
		height: 100%;
		align-items: flex-start;
		flex-wrap: wrap;
		> * {
			flex: 1 0 450px;
			max-width: 600px;
			margin: 0 auto;
		}
		&--description {
			padding: 50px 90px 0 0;
			h2 {
				font-size: 50px;
				font-weight: 400;
			}
			p {
				font-size: 20px;
				border-left: 1px solid #65B9F4;
				padding-left: 16px;
				margin-top: 60px;
				line-height: 28px;
				color: #383838;
			}
		}
		&--list {
			font-size: 25px;
			display: flex;
			flex-direction: column;
			border-bottom: 1px solid #65B9F4;
			.item {
				padding: 30px 0 20px;
				border-top: 1px solid #65B9F4;
				h3 {
					font-weight: 400;
				}
				.text {
					margin-top: 20px;
					font-size: 18px;
					color: #8F8F8F;
				}
			}
		}
	}
}
</style>