<template>
	<section class="results">
		<div class="results__content">
			<h2 class="mobile-heading">Результат обучения</h2>
			<div class="results__content--left">
				<h2 class="heading">Результат обучения</h2>
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
				<p class="first-line">
					Вы станете Middle AI developer и сможете претендовать на любые AI вакансии или брать AI проекты на заказ.<br>
					Так же вы сможете реализовывать свои собственные проекты, как хобби или для создания стартапа
				</p>
				<h3><span>Трудоустройство</span></h3>
				<p class="second-line">
					Мы гарантируем трудоустройство по договору.<br>
					Если вы не программист, то ваша зарплата сразу после обучения будет 70-100 тысяч рублей в месяц.<br>
					Если вы программист - то 100-200 тысяч рублей в месяц
				</p>
				<div class="cv-mobile">
					<img :src="require('../assets/cv1.png')" alt="Резюме 1" width="144">
					<img :src="require('../assets/cv2.png')" alt="Резюме 2" width="144" class="shifted">
					<p>Помогаем в составлении резюме</p>
				</div>
				<h3><span>AI проект</span></h3>
				<p>
					Вы создадите собственный AI проект в процессе обучения.<br>
					Это может быть проект для вашей компании или проект который вы создадите для себя и будете применять в своей работе.<br>
					Некоторые студенты делают проекты просто для интереса или для запуска собственного стартапа
				</p>
				<div class="project-mobile">
					<img :src="require('../assets/project.png')" alt="Пример проекта" width="500">
					<p>Опубликованный AI проект</p>
				</div>
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
	.mobile-heading, .cv-mobile, .project-mobile {
		display: none;
	}
	&__content {
		display: flex;
		flex-wrap: wrap;
		gap: 50px;
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
				line-height: 1.4em;
				color: #383838;
				margin: 16px 0 40px;
				font-family: 'Inter', sans-serif;
				padding-left: 10px;
				position: relative;
				&.first-line::after {
					content: '';
					position: absolute;
					bottom: -65px;
					width: 194px;
					right: 100%;
					height: 1px;
					background: #65B9F4;
				}
				&.second-line::after {
					content: '';
					position: absolute;
					bottom: -65px;
					width: 112px;
					right: 100%;
					height: 1px;
					background: #65B9F4;
				}
			}
		}
		&--left {
			position: relative;
			margin-bottom: 50px;
			.project img {
				width: 100%;
			}
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
			p {
				font-size: 18px;
				line-height: 1.38em;
				color: #9C9C9C;
			}
		}
		h2 {
			font-size: 50px;
			color: #000;
			line-height: 1.16em;
			font-weight: 400;
			margin-bottom: 35px;
		}
	}
}

@media (max-width: 1190px) {
	.results {
		&__content {
			padding: 100px 20px 100px 40px;
			> * {
				flex: 1 1 320px;
			}
			&--left {
				.shifted {
					margin: 0;
				}
				h2 {
					font-size: 40px;
					margin-bottom: 48px;
				}
				.cv {
					display: flex;
					justify-content: space-between;
					flex-wrap: wrap;
					> * {
						flex: 0 1 180px;
					}
				}
			}
			&--right {
				h3 {
					font-size: 20px;
				}
				p {
					font-size: 18px;
					&.first-line::after {
						content: '';
						position: absolute;
						width: 60px;
					}
					&.second-line::after {
						content: '';
						position: absolute;
						width: 54px;
					}
				}
			}
		}
	}
}

@media (max-width: 860px) {
	.results {
		&__content {
			padding: 100px 20px 100px 40px;
			.mobile-heading {
				display: block;
				flex: 1 0 100%;
				margin: 0;
			}
			.heading {
				display: none;
			}
			> * {
				flex: 1 1 320px;
			}
			&--left {
				p {
					font-size: 14px;
				}
				.shifted {
					margin: 0;
					transform: translateY(35px);
				}
				h2 {
					font-size: 40px;
					margin-bottom: 48px;
				}
				.cv {
					display: flex;
					justify-content: space-between;
					flex-wrap: wrap;
					img {
						width: 100%;
					}
					> * {
						flex: 0 1 144px;
					}
				}
			}
			&--right {
				h3 {
					font-size: 20px;
				}
				p {
					font-size: 16px;
					&.first-line::after {
						display: none;
					}
					&.second-line::after {
						display: none;
					}
				}
			}
		}
	}
}

@media (max-width: 550px) {
	.results {
		h2 {
			font-size: 30px;
			padding: 0 10px;
		}
		&__content {
			padding: 100px 0;
			&--left {
				display: none;
			}
			&--right {
				width: 100%;
			}
			.project-mobile img {
				width: 100%;
				margin: 0 10px;
			}
			.cv-mobile, .project-mobile {
				display: flex;
				flex-wrap: wrap;
				gap: 10px;
				p {
					padding: 0;
					color: #9C9C9C;
				}
			}
			.project-mobile p {
				margin: 0;
				padding-left: 10px;
				margin-top: 10px;
			}
			.cv-mobile {
				width: 300px;
				margin: auto;
				p {
					flex-basis: 150px;
					font-size: 14px;
				}
				.shifted {
					transform: translateY(65px);
				}
			}
		}
	}
}
</style>