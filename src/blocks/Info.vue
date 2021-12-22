<template>
	<section class="info">
		<div class="info__content">
			<div class="info__content--description">
				<h2>Что будет на дне открытых дверей</h2>
				<p>Вы узнаете все подробности об обучении на курсе "Data science и нейронные сети" <br>
					Это позволит вам принимать взвешенное решение об обучении и понять для, каких результатов вы сможете достичь
				</p>
			</div>
			<ol class="info__content--list">
				<li><b>1</b><span>С какими целями стоит идти на обучение</span></li>
				<li><b>2</b><span>Как проходит обучение</span></li>
				<li><b>3</b><span>Программа обучения</span></li>
				<li><b>4</b><span>Как мы трудоустраиваем выпускников</span></li>
				<li><b>5</b><span>Как вы можете создать AI проект во время обучения</span></li>
				<li><b>6</b><span>Какой уровень нужен для старта обучения</span></li>
				<li><b>7</b><span>Примеры 98 созданных нашими студентами AI проектов</span></li>
				<li><b>8</b><span>Тарифы и цены</span></li>
			</ol>
		</div>
	</section>
</template>

<script>
export default {
	name: 'Info'
}
</script>

<style lang="scss" scoped>
.info {
	background: #3F5168;
	&__content {
		display: flex;
		height: 100%;
		align-items: flex-start;
		flex-wrap: wrap;
		> * {
			flex: 1 0 400px;
			max-width: 600px;
			margin: 0 auto;
		}
		&--description {
			border-top: 1px solid #65B9F4;
			padding: 50px 90px 0 0;
			h2 {
				font-size: 50px;
				line-height: 1.15em;
				color: #FFFFFF;
				font-weight: 400;
			}
			p {
				color: #D0D0D0;
				font-size: 20px;
				border-left: 1px solid #65B9F4;
				padding-left: 16px;
				margin-top: 60px;
				line-height: 1.4em;
				font-family: 'Inter', sans-serif;
			}
		}
		&--list {
			list-style: none;
			padding: 0;
			color: #FFFFFF;
			font-size: 25px;
			line-height: 1.4em;
			border-left: 1px solid #65B9F4;
			border-bottom: 1px solid #65B9F4;
			li {
				height: 98px;
				display: flex;
				align-items: center;
				padding: 7px 14px;
				gap: 25px;
				position: relative;
				&::after {
					content: '';
					width: 123px;
					position: absolute;
					top: 100%;
					left: 0;
					height: 1px;
					background-color: #65B9F4;
				}
				b {
					color: #3F5168;
					font-size: 70px;
					user-select: none;
					text-shadow: -1px -1px 0 #FF8B60,
												1px -1px 0 #FF8B60,
												-1px 1px 0 #FF8B60,
												1px 1px 0 #FF8B60,
												0px 0px 10px rgba(164, 228, 237, 0.15);
					opacity: .4;
				}
			}
		}
	}
}

@media (max-width: 1240px) {
	.info {
		&__content {
			&--description {
				padding: 50px 90px 0 40px;
				p {
					font-size: 18px;
				}
				h2 {
					font-size: 40px;
				}
			}
			&--list {
				font-size: 20px;
			}
		}
	}
}

@media (max-width: 860px) {
	.info {
		&__content {
			padding: 100px 40px;
			&--description {
				padding: 0;
				margin: 0;
				margin-bottom: 90px;
				border: none;
				h2 {
					font-size: 30px;
				}
				p {
					font-size: 16px;
				}
			}
			&--list {
				margin: 0;
			}
		}
	}
}

@media (max-width: 550px) {
	.info {
		&__content {
			padding: 100px 10px;
			> * {
				flex-shrink: 1;
			}
			&--description {
				padding: 0;
				margin: 0;
				margin-bottom: 90px;
				border: none;
				h2 {
					font-size: 30px;
				}
				p {
					font-size: 16px;
					margin-top: 40px;
				}
			}
			&--list {
				margin: 0;
				li {
					padding: 5px 0 5px 10px;
				}
			}
		}
	}
}
</style>