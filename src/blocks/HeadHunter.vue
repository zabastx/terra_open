<template>
	<section class="headhunter">
		<div class="headhunter__content">
			<div class="headhunter__content--left">
				<h2>Data scientist - профессия будущего</h2>
				<p class="heading-mobile">
					В ближайшие годы навыки создания AI станут обязательными для всех программистов, специалистов и управленцев так же, как недавно обязательными стали навыки работы в интернете
				</p>
				<div class="block first">
					<h3>800 вакансий</h3>
					<p>Более 800 вакансий на hh.ru</p>
				</div>
				<div class="block second">
					<h3>Зарплаты от 150 000 руб.</h3>
					<p>Средние зарплаты от 150 000 руб. и выше</p>
				</div>
				<div class="block third">
					<h3>Топ-5 профессий</h3>
					<p>Профессия №1 в США и Китае, входит в топ-5 профессий в России</p>
				</div>
				<div class="block fourth">
					<h3>Рост в 2 раза</h3>
					<p>Количество вакансий растет в 2 раза за год</p>
				</div>
			</div>
			<div class="headhunter__content--right">
				<p class="heading">
					В ближайшие годы навыки создания AI станут обязательными для всех программистов, специалистов и управленцев так же, как недавно обязательными стали навыки работы в интернете
				</p>
				<div class="img-block">
					<img :src="require('../assets/hh/header.png')" alt="hh.ru">
					<img :src="require('../assets/hh/1.png')" alt="Вакансия 1">
					<img :src="require('../assets/hh/2.png')" alt="Вакансия 2">
					<img :src="require('../assets/hh/3.png')" alt="Вакансия 3" style="z-index: 1;">
					<img :src="require('../assets/hh/4.png')" alt="Вакансия 4" style="z-index: 2;">
				</div>
			</div>
		</div>
	</section>
</template>

<script>
export default {
	name: 'HeadHunter'
}
</script>

<style lang="scss" scoped>
.headhunter {
	background: #EBF2F6;
	font-family: 'Inter', sans-serif;
	.heading-mobile {
		display: none;
		font-size: 16px;
		border-left: 1px solid #65B9F4;
		padding-left: 15px;
		margin-bottom: 70px;
		color: #383838;
	}
	&__content {
		display: flex;
		flex-wrap: wrap;
		> * {
			flex: 1 1 400px;
		}
		&--left {
			h2 {
				font-weight: 400;
				font-size: 50px;
				line-height: 1.16em;
				color: #000;
				margin-bottom: 90px;
				font-family: 'Play', sans-serif;
			}
			.block {
				margin-bottom: 75px;
				position: relative;
				h3 {
					font-weight: 600;
					color: #FF8B60;
					font-size: 25px;
					line-height: 1.2em;
					margin-bottom: 20px;
				}
				&::after {
					content: '';
					position: absolute;
					left: -38px;
					top: -13px;
				}
			}
		}
		&--right {
			p {
				font-size: 20px;
				line-height: 1.4em;
				color: #383838;
				border-left: 1px solid #65B9F4;
				padding-left: 15px;
			}
			.img-block {
				padding-bottom: 160px;
				display: flex;
				flex-direction: column;
				align-items: flex-start;
				img {
					margin-bottom: -160px;
					margin-top: 100px;
					&:nth-child(2n+1) {
						margin-top: 60px;
						transform: translateX(50%);
					}
					&:first-child {
						margin: 100px 0 -70px;
						transform: translateX(0);
						width: 100%;
					}
				}
			}
		}
	}
}

@media (max-width: 1240px) {
	.headhunter {
		&__content {
			padding: 100px 20px 100px 40px;
			> * {
				flex: 1 1 300px;
			}
			&--left {
				h2 {
					font-size: 40px;
				}
				.block {
					margin-bottom: 40px;
					h3 {
						font-size: 20px;
					}
					p {
						font-size: 18px;
					}
				}
			}
			&--right {
				display: flex;
				flex-direction: column;
				p {
					font-size: 18px;
				}
				.img-block {
					img {
						width: 66%;
						margin-bottom: -140px;
						&:first-child {
							margin-top: 50px;
						}
					}
				}
			}
		}
	}
}

@media (max-width: 860px) {
	.headhunter {
		.heading-mobile {
			display: block;
		}
		.heading {
			display: none;
		}
		&__content {
			> * {
				flex: 1 1 400px;
				max-width: 520px;
			}
			&--left {
				h2 {
					font-size: 30px;
					margin-bottom: 50px;
				}
				.block p {
					font-size: 16px;
				}
			}
		}
	}
}

@media (max-width: 550px) {
	.headhunter {
		&__content {
			padding: 100px 10px;
			&--right {
				.img-block {
					padding: 0;
					img {
						width: 80%;
						margin: 0;
						&:nth-child(2n+1) {
							margin: 0;
							transform: translateX(0);
							margin-left: auto;
						}
						&:first-child {
							margin: 0;
							margin-bottom: 10px;
						}
					}
				}
			}
		}
	}
}
</style>