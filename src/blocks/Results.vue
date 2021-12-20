<template>
	<section class="results">
		<div class="results__content">
			<div class="results__content--left">
				<h2>Результат обучения</h2>
				<div class="cv">
					<img :src="require('../assets/cv1.png')" alt="Резюме 1" width="182">
					<img :src="require('../assets/cv2.png')" alt="Резюме 2" width="182" class="shifted">
					<p>Помогаем в составлении резюме</p>
				</div>
				<div class="project">
					<img :src="require('../assets/project.png')" alt="Пример проекта" width="500">
					<p>Опубликованный AI проект</p>
				</div>
			</div>
			<div class="results__content--right">
				<h3><span>Профессия</span></h3>
				<p>
					Вы станете Middle AI developer и сможете претендовать на любые AI вакансии или брать AI проекты на заказ.<br>
					Так же вы сможете реализовывать свои собственные проекты, как хобби или для создания стартапа
				</p>
				<h3><span>Трудоустройство</span></h3>
				<p>
					Мы гарантируем трудоустройство по договору.<br>
					Если вы не программист, то ваша зарплата сразу после обучения будет 70-100 тысяч рублей в месяц.<br>
					Если вы программист - то 100-200 тысяч рублей в месяц
				</p>
				<h3><span>AI проект</span></h3>
				<p>
					Вы создадите собственный AI проект в процессе обучения.<br>
					Это может быть проект для вашей компании или проект который вы создадите для себя и будете применять в своей работе.<br>
					Некоторые студенты делают проекты просто для интереса или для запуска собственного стартапа
				</p>
			</div>
		</div>
	</section>
</template>

<script>
export default {
	name: 'Results'
}
</script>

<style lang="scss" scoped>
.results {
	background: #EFEFEF;
	&__content {
		display: flex;
		flex-wrap: wrap;
		padding-bottom: 100px;
		> * {
			flex: 1 0 450px;
			max-width: 600px;
			margin: 0 auto;
		}
		&--right {
			h3 {
				color: #FF8B60;
				line-height: 47px;
				padding: 0 11px;
				width: max-content;
				border: 1px solid #65B9F4;
  			position: relative;
				&::before, &::after {
					content: '';
					display: block;
					position: absolute;
					background: #efefef;
				}
				
				&::before {
					top: -1px;
					bottom: -1px;
					left: 25%;
					right: 25%;
				}
				
				&::after{
					left: -1px;
					right: -1px;
					height: 25px;
					top: 50%;
					transform: translateY(-50%);
				}
				span {
					position: relative;
    			z-index: 1;
				}
			}
			p {
				font-size: 20px;
				line-height: 28px;
				color: #383838;
				margin: 10px 0 40px;
			}
		}
		&--left {
			position: relative;
			margin-bottom: 50px;
			.cv {
				margin-bottom: 45px;
				img + p {
					width: 190px;
				}
			}
			.shifted {
				transform: translateY(70px);
				margin-left: 36px;
			}
			h2 {
				font-size: 50px;
				color: #000;
				line-height: 58px;
				font-weight: 400;
				margin-bottom: 35px;
			}
			p {
				font-size: 18px;
				line-height: 25px;
				color: #9C9C9C;
			}
			&::after {
				content: '';
				position: absolute;
				top: 235px;
				height: 1px;
				left: 394px;
				right: 10px;
				background: #65B9F4;
			}
			&::before {
				content: '';
				position: absolute;
				top: 448px;
				height: 1px;
				left: 440px;
				right: 10px;
				background: #65B9F4;
			}
		}
	}
}
</style>