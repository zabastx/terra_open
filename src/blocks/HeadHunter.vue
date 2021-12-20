<template>
	<section class="headhunter">
		<div class="headhunter__content">
			<div class="headhunter__content--left">
				<h2>Data scientist - профессия будущего</h2>
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
				<p>
					В ближайшие годы навыки создания AI станут обязательными для всех программистов, специалистов и управленцев так же, как недавно обязательными стали навыки работы в интернете
				</p>
				<div class="img-block">
					<img :src="require('../assets/hh/header.png')" :srcset="require('../assets/hh/header.webp')" alt="hh.ru">
					<img :src="require('../assets/hh/1.png')" :srcset="require('../assets/hh/1.webp')" alt="Вакансия 1">
					<img :src="require('../assets/hh/2.png')" :srcset="require('../assets/hh/2.webp')" alt="Вакансия 2">
					<img :src="require('../assets/hh/3.png')" :srcset="require('../assets/hh/3.webp')" alt="Вакансия 3">
					<img :src="require('../assets/hh/4.png')" :srcset="require('../assets/hh/4.webp')" alt="Вакансия 4">
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
	&__content {
		display: flex;
		flex-wrap: wrap;
		> * {
			flex: 1 0 450px;
		}
		&--left {
			h2 {
				font-weight: 400;
				font-size: 50px;
				line-height: 58px;
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
					line-height: 30px;
					margin-bottom: 20px;
				}
				&::after {
					content: '';
					position: absolute;
					left: -38px;
					top: -13px;
				}
				&.first::after {
					background: no-repeat url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNjg4IiBoZWlnaHQ9IjExMyIgdmlld0JveD0iMCAwIDY4OCAxMTMiIGZpbGw9Im5vbmUiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxwYXRoIGQ9Ik0wLjUgMFY4Ny41ODU4QzAuNSA4Ny44NTEgMC42MDUzNTcgODguMTA1NCAwLjc5Mjg5MyA4OC4yOTI5TDI0LjIwNzEgMTExLjcwN0MyNC4zOTQ2IDExMS44OTUgMjQuNjQ5IDExMiAyNC45MTQyIDExMkgzNDUuMDg2QzM0NS4zNTEgMTEyIDM0NS42MDUgMTExLjg5NSAzNDUuNzkzIDExMS43MDdMNDAyLjcwNyA1NC43OTI5QzQwMi44OTUgNTQuNjA1NCA0MDMuMTQ5IDU0LjUgNDAzLjQxNCA1NC41SDY4Ny41IiBzdHJva2U9IiM2NUI5RjQiIHN0cm9rZS1vcGFjaXR5PSIwLjMiLz4KPC9zdmc+Cg==');
					width: 687px;
					height: 112px;
				}
				&.second::after {
					background: no-repeat url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNjQzIiBoZWlnaHQ9IjExMyIgdmlld0JveD0iMCAwIDY0MyAxMTMiIGZpbGw9Im5vbmUiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxwYXRoIGQ9Ik0xIDBWODcuNTg1OEMxIDg3Ljg1MSAxLjEwNTM2IDg4LjEwNTQgMS4yOTI4OSA4OC4yOTI5TDI0LjcwNzEgMTExLjcwN0MyNC44OTQ2IDExMS44OTUgMjUuMTQ5IDExMiAyNS40MTQyIDExMkg0NjUuNzA5QzQ2NS44OTkgMTEyIDQ2Ni4wODUgMTExLjk0NiA0NjYuMjQ2IDExMS44NDRMNDkzLjI1NCA5NC42NTYzQzQ5My40MTUgOTQuNTU0MiA0OTMuNjAxIDk0LjUgNDkzLjc5MSA5NC41SDY0MyIgc3Ryb2tlPSIjNjVCOUY0IiBzdHJva2Utb3BhY2l0eT0iMC4zIi8+Cjwvc3ZnPgo=');
					width: 642px;
					height: 112px;
				}
				&.third::after {
					background: no-repeat url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNDY2IiBoZWlnaHQ9IjEzMyIgdmlld0JveD0iMCAwIDQ2NiAxMzMiIGZpbGw9Im5vbmUiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxwYXRoIGQ9Ik0xIDBWMTA3LjU4NkMxIDEwNy44NTEgMS4xMDUzNiAxMDguMTA1IDEuMjkyODkgMTA4LjI5M0wyNC43MDcxIDEzMS43MDdDMjQuODk0NiAxMzEuODk1IDI1LjE0OSAxMzIgMjUuNDE0MiAxMzJINDY2IiBzdHJva2U9IiM2NUI5RjQiIHN0cm9rZS1vcGFjaXR5PSIwLjMiLz4KPC9zdmc+Cg==');
					width: 465px;
					height: 132px;
				}
				&.fourth::after {
					background: no-repeat url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTQ0MCIgaGVpZ2h0PSIyOTEiIHZpZXdCb3g9IjAgMCAxNDQwIDI5MSIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggZD0iTTEgMFY5Ny41ODU4QzEgOTcuODUxIDEuMTA1MzYgOTguMTA1NCAxLjI5Mjg5IDk4LjI5MjlMMjQuNzA3MSAxMjEuNzA3QzI0Ljg5NDYgMTIxLjg5NSAyNS4xNDkgMTIyIDI1LjQxNDIgMTIySDQ5NS41ODZDNDk1Ljg1MSAxMjIgNDk2LjEwNSAxMjEuODk1IDQ5Ni4yOTMgMTIxLjcwN0w1NDMuMjA3IDc0Ljc5MjlDNTQzLjM5NSA3NC42MDU0IDU0My42NDkgNzQuNSA1NDMuOTE0IDc0LjVINjE2LjVDNjE3LjA1MiA3NC41IDYxNy41IDc0Ljk0NzcgNjE3LjUgNzUuNVYxOTVDNjE3LjUgMTk1LjU1MiA2MTcuOTQ4IDE5NiA2MTguNSAxOTZIODM4LjVDODM5LjA1MiAxOTYgODM5LjUgMTk2LjQ0OCA4MzkuNSAxOTdWMjg5QzgzOS41IDI4OS41NTIgODM5Ljk0OCAyOTAgODQwLjUgMjkwSDE5MDAuNSIgc3Ryb2tlPSIjNjVCOUY0IiBzdHJva2Utb3BhY2l0eT0iMC4zIi8+Cjwvc3ZnPgo=');
					width: 1900px;
					height: 290px;
				}
			}
		}
		&--right {
			p {
				font-size: 20px;
				line-height: 28px;
				color: #383838;
				border-left: 1px solid #65B9F4;
				padding-left: 15px;
			}
			.img-block {
				padding-bottom: 160px;
				img {
					margin-bottom: -160px;
					margin-top: 100px;
					&:nth-child(2n+1) {
						margin-left: 210px;
						margin-top: 60px;
					}
					&:first-child {
						margin: 100px 0 -70px;
					}
				}
			}
		}
	}
}
</style>