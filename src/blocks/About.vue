<template>
	<section class="about">
		<h2>Университет<br>искусственного интеллекта</h2>
		<div class="about__content">
			<div class="about__content--images">
				<picture class="first">
					<img :src="require('../assets/about/1.png')" :srcset="require('../assets/about/1.webp')" alt="Фото с занятий 1">
				</picture>
				<picture class="second">
					<img :src="require('../assets/about/2.png')" :srcset="require('../assets/about/2.webp')" alt="Фото с занятий 2">
				</picture>
				<picture class="third">
					<img :src="require('../assets/about/3.png')" :srcset="require('../assets/about/3.webp')" alt="Фото с занятий 3">
				</picture>
			</div>
			<div class="about__content--info">
				<h3>№1 в России</h3>
				<p>AI образование #1 в России</p>
				<h3>c 2018 года</h3>
				<p>Основан в августе 2018 года</p>
				<h3>Собственник - AI разработчик</h3>
				<p>Собственник компании - AI разработчик с 18-ти летним опытом</p>
				<h3>Аутсорс компания</h3>
				<p>Университет является аутсорс компанией в области AI, мы разрабатываем AI проекты на заказ</p>
				<h3>Свой AI софт Terra AI</h3>
				<p>Создаёт ведущий AI софт Terra AI по созданию нейронных сетей без программирования</p>
			</div>
		</div>
	</section>
</template>

<script>
export default {
	name: 'About'
}
</script>

<style lang="scss" scoped>
.about {
	background: no-repeat url('../assets/aboutbg.svg');
	background-color: #3F5168;
	background-position: calc(100% - 33px) 33px;
	h2 {
		color: #F8F8F8;
		font-weight: 400;
		font-size: 50px;
		line-height: 58px;
		padding-bottom: 100px;
	}
	&__content {
		padding-top: 0;
		display: flex;
		flex-wrap: wrap;
		> * {
			flex: 1 0 450px;
			max-width: 600px;
			margin: auto;
		}
		&--images {
			padding-right: 100px;
			display: flex;
			flex-direction: column;
			align-items: flex-start;
			img {
				display: block;
			}
			picture {
				position: relative;
			}
			.first {
				margin-bottom: 27px;
				&::after {
					content: '';
					position: absolute;
					left: calc(100% - 60px);
					top: -30px;
					height: 230px;
					width: 235px;
					background: no-repeat url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjM1IiBoZWlnaHQ9IjIzMCIgdmlld0JveD0iMCAwIDIzNSAyMzAiIGZpbGw9Im5vbmUiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxwYXRoIGQ9Ik00LjcwMzg2IDkuNDA4NzhDNS44NDMzNyA5LjQwNzY1IDYuOTQzOCA4Ljk5MzE3IDcuODAwOTggOC4yNDIyMkM4LjY1ODE1IDcuNDkxMjcgOS4yMTM4OSA2LjQ1NDg0IDkuMzY1MDggNS4zMjUyMkg3MC40NzM2TDY5Ljc2MjggMjI5LjYxOEgyMTUuNDYyTDIyNy4zODcgMjE3LjY4OEMyMjguMzU4IDIxOC4zNzYgMjI5LjU1NCAyMTguNjcgMjMwLjczNCAyMTguNTFDMjMxLjkxMyAyMTguMzUgMjMyLjk4NyAyMTcuNzQ3IDIzMy43MzkgMjE2LjgyNEMyMzQuNDkxIDIxNS45MDIgMjM0Ljg2NCAyMTQuNzI3IDIzNC43ODMgMjEzLjU0QzIzNC43MDIgMjEyLjM1MiAyMzQuMTcyIDIxMS4yNCAyMzMuMzAyIDIxMC40MjhDMjMyLjQzMSAyMDkuNjE2IDIzMS4yODUgMjA5LjE2NSAyMzAuMDk1IDIwOS4xNjdDMjI4LjkwNCAyMDkuMTY5IDIyNy43NTkgMjA5LjYyMyAyMjYuODkxIDIxMC40MzhDMjI2LjAyMyAyMTEuMjUyIDIyNS40OTcgMjEyLjM2NiAyMjUuNDIgMjEzLjU1NEMyMjUuMzQyIDIxNC43NDIgMjI1LjcxOSAyMTUuOTE1IDIyNi40NzQgMjE2LjgzNkwyMTQuOTU3IDIyOC4zNjlINzAuMzA2NEw3MS4wMTcyIDQuMDc1ODZIOS4zNjUwOEM5LjI0NDM3IDMuMTgwMzQgOC44NjgzMyAyLjMzODUzIDguMjgxOTQgMS42NTEwOUM3LjY5NTU2IDAuOTYzNjQ5IDYuOTIzNjQgMC40NTk2NjUgNi4wNTg0NiAwLjE5OTM4NEM1LjE5MzI3IC0wLjA2MDg5NjMgNC4yNzE0NSAtMC4wNjY0NTk2IDMuNDAzMTkgMC4xODMzNjhDMi41MzQ5MyAwLjQzMzE5NiAxLjc1Njk5IDAuOTI3ODQyIDEuMTYyMzYgMS42MDgxNkMwLjU2NzczNiAyLjI4ODQ4IDAuMTgxNTkgMy4xMjU2OSAwLjA1MDA5MjUgNC4wMTk2OUMtMC4wODE0MDQ4IDQuOTEzNjkgMC4wNDcyOTMyIDUuODI2NjUgMC40MjA4MzQgNi42NDk0MkMwLjc5NDM3NSA3LjQ3MjE5IDEuMzk2OTUgOC4xNjk5NiAyLjE1NjQ4IDguNjU5MjlDMi45MTYwMiA5LjE0ODYzIDMuODAwMzggOS40MDg4MyA0LjcwMzg2IDkuNDA4NzhaIiBmaWxsPSIjNEI2ODg0Ii8+Cjwvc3ZnPgo='),
					no-repeat 70% 95% url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTE5IiBoZWlnaHQ9IjEyIiB2aWV3Qm94PSIwIDAgMTE5IDEyIiBmaWxsPSJub25lIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciPgo8cGF0aCBkPSJNMi4yOTU4NSAwLjA2Mjk2MTVMMCAyLjM1ODRMOS4xODAyMiAxMS41NDM0TDExLjQ3NjEgOS4yNDc5M0wyLjI5NTg1IDAuMDYyOTYxNVoiIGZpbGw9IiM0QjY4ODQiLz4KPHBhdGggZD0iTTEwLjUwMzkgMC4wMDQzNjA1M0w4LjIwODAxIDIuMjk5OEwxNy4zODgzIDExLjQ4NDdMMTkuNjg0MSA5LjE4OTI5TDEwLjUwMzkgMC4wMDQzNjA1M1oiIGZpbGw9IiM0QjY4ODQiLz4KPHBhdGggZD0iTTE4LjczNTMgMC4wMDQzNjc3NEwxNi40Mzk1IDIuMjk5OEwyNS42MTk3IDExLjQ4NDhMMjcuOTE1NiA5LjE4OTM0TDE4LjczNTMgMC4wMDQzNjc3NFoiIGZpbGw9IiM0QjY4ODQiLz4KPHBhdGggZD0iTTI2Ljk2NTggMC4wMDA0NTU0MTdMMjQuNjY5OSAyLjI5NTlMMzMuODUwMyAxMS40ODA5TDM2LjE0NjIgOS4xODU0NUwyNi45NjU4IDAuMDAwNDU1NDE3WiIgZmlsbD0iIzRCNjg4NCIvPgo8cGF0aCBkPSJNMzUuMjAyMSAwLjAzMTcxMTRMMzIuOTA2MiAyLjMyNzE1TDQyLjA4NjQgMTEuNTEyMUw0NC4zODIzIDkuMjE2NjhMMzUuMjAyMSAwLjAzMTcxMTRaIiBmaWxsPSIjNEI2ODg0Ii8+CjxwYXRoIGQ9Ik00My40MzM1IDAuMDI3ODEyNUw0MS4xMzc3IDIuMzIzMjRMNTAuMzE3OSAxMS41MDgzTDUyLjYxMzcgOS4yMTI4Mkw0My40MzM1IDAuMDI3ODEyNVoiIGZpbGw9IiM0QjY4ODQiLz4KPHBhdGggZD0iTTUxLjY1NjcgMC4wMDgyOTMzN0w0OS4zNjA4IDIuMzAzNzFMNTguNTQxMiAxMS40ODg3TDYwLjgzNyA5LjE5MzI1TDUxLjY1NjcgMC4wMDgyOTMzN1oiIGZpbGw9IiM0QjY4ODQiLz4KPHBhdGggZD0iTTU5LjkwNzYgMC4wNTU1MzI2TDU3LjYxMTMgMi4zNTA1OUw2Ni43ODk5IDExLjUzNzJMNjkuMDg2MiA5LjI0MjExTDU5LjkwNzYgMC4wNTU1MzI2WiIgZmlsbD0iIzRCNjg4NCIvPgo8cGF0aCBkPSJNNjguMTI2NCAwLjAyMzg3OTVMNjUuODMwNiAyLjMxOTM0TDc1LjAxMDggMTEuNTA0M0w3Ny4zMDY3IDkuMjA4ODZMNjguMTI2NCAwLjAyMzg3OTVaIiBmaWxsPSIjNEI2ODg0Ii8+CjxwYXRoIGQ9Ik03Ni4zNzMgMC4wNjI5NjA1TDc0LjA3NzEgMi4zNTg0TDgzLjI1NzQgMTEuNTQzM0w4NS41NTMyIDkuMjQ3ODdMNzYuMzczIDAuMDYyOTYwNVoiIGZpbGw9IiM0QjY4ODQiLz4KPHBhdGggZD0iTTg0LjU5MjcgMC4wMzU2MjVMODIuMjk2OSAyLjMzMTA1TDkxLjQ3NzEgMTEuNTE2MUw5My43NzI5IDkuMjIwNjNMODQuNTkyNyAwLjAzNTYyNVoiIGZpbGw9IiM0QjY4ODQiLz4KPHBhdGggZD0iTTkyLjgyMDIgMC4wMjM5MjQ1TDkwLjUyNDQgMi4zMTkzNEw5OS43MDQ2IDExLjUwNDNMMTAyIDkuMjA4ODZMOTIuODIwMiAwLjAyMzkyNDVaIiBmaWxsPSIjNEI2ODg0Ii8+CjxwYXRoIGQ9Ik0xMDEuMDQ5IDAuMDIzNDcwMUw5OC43NTM5IDIuMzE5MzRMMTA3LjkzNiAxMS41MDI3TDExMC4yMzEgOS4yMDY4OEwxMDEuMDQ5IDAuMDIzNDcwMVoiIGZpbGw9IiM0QjY4ODQiLz4KPHBhdGggZD0iTTEwOS4zMDIgMC4wNjY4NjA2TDEwNy4wMDYgMi4zNjIzTDExNi4xODYgMTEuNTQ3MkwxMTguNDgyIDkuMjUxNzlMMTA5LjMwMiAwLjA2Njg2MDZaIiBmaWxsPSIjNEI2ODg0Ii8+Cjwvc3ZnPgo=');
				}
			}
			.second {
				margin-left: auto;
				&::before {
					content: '';
					position: absolute;
					width: 290px;
					height: 30px;
					top: -15px;
					right: calc(100% - 70px);
					background: no-repeat url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjkwIiBoZWlnaHQ9IjMwIiB2aWV3Qm94PSIwIDAgMjkwIDMwIiBmaWxsPSJub25lIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciPgo8cGF0aCBkPSJNMjg1LjA5IDkuNDA4NzhDMjgzLjk1MSA5LjQwNzY1IDI4Mi44NSA4Ljk5MzE3IDI4MS45OTMgOC4yNDIyMkMyODEuMTM2IDcuNDkxMjcgMjgwLjU4IDYuNDU0ODQgMjgwLjQyOSA1LjMyNTIySDIxOS4zMkwxOTUuMDMxIDI5LjYxODRIMTkuMzMxNUw3LjQwNjY1IDE3LjY4NzdDNi40MzU4NSAxOC4zNzY0IDUuMjM5NjIgMTguNjcwNCA0LjA2MDI0IDE4LjUxMDFDMi44ODA4NiAxOC4zNDk4IDEuODA2NDkgMTcuNzQ3MiAxLjA1NDY2IDE2LjgyNDRDMC4zMDI4MjYgMTUuOTAxNSAtMC4wNzAyNTE1IDE0LjcyNzQgMC4wMTA5NTU4IDEzLjUzOThDMC4wOTIxOTM2IDEyLjM1MjEgMC42MjE2NzQgMTEuMjM5NyAxLjQ5MjE2IDEwLjQyNzlDMi4zNjI2NCA5LjYxNjAzIDMuNTA5MDYgOS4xNjUzOSA0LjY5OTI4IDkuMTY3MjJDNS44ODk1IDkuMTY5MDUgNy4wMzQ1OCA5LjYyMzIyIDcuOTAyNTYgMTAuNDM3N0M4Ljc3MDU0IDExLjI1MjMgOS4yOTY1NCAxMi4zNjYzIDkuMzc0MTEgMTMuNTU0MUM5LjQ1MTcyIDE0Ljc0MiA5LjA3NTA0IDE1LjkxNSA4LjMyMDM3IDE2LjgzNTZMMTkuODM2NSAyOC4zNjlIMTk0LjQ4N0wyMTguNzc3IDQuMDc1ODZIMjgwLjQyOUMyODAuNTUgMy4xODAzNCAyODAuOTI2IDIuMzM4NTMgMjgxLjUxMiAxLjY1MTA5QzI4Mi4wOTggMC45NjM2NDkgMjgyLjg3IDAuNDU5NjY1IDI4My43MzUgMC4xOTkzODRDMjg0LjYwMSAtMC4wNjA4OTYzIDI4NS41MjIgLTAuMDY2NDU5NiAyODYuMzkxIDAuMTgzMzY4QzI4Ny4yNTkgMC40MzMxOTYgMjg4LjAzNyAwLjkyNzg0MiAyODguNjMyIDEuNjA4MTZDMjg5LjIyNiAyLjI4ODQ4IDI4OS42MTIgMy4xMjU2OSAyODkuNzQ0IDQuMDE5NjlDMjg5Ljg3NSA0LjkxMzY5IDI4OS43NDcgNS44MjY2NSAyODkuMzczIDYuNjQ5NDJDMjg5IDcuNDcyMTkgMjg4LjM5NyA4LjE2OTk2IDI4Ny42MzcgOC42NTkyOUMyODYuODc4IDkuMTQ4NjMgMjg1Ljk5NCA5LjQwODgzIDI4NS4wOSA5LjQwODc4WiIgZmlsbD0iIzRCNjg4NCIvPgo8L3N2Zz4K');
				}
				&::after {
					content: '';
					position: absolute;
					left: -10px;
					top: calc(100% + 12px);
					width: 300px;
					height: 82px;
					background: no-repeat url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMzAwIiBoZWlnaHQ9IjgyIiB2aWV3Qm94PSIwIDAgMzAwIDgyIiBmaWxsPSJub25lIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciPgo8cGF0aCBkPSJNMjk1LjA5IDIwLjIwODZDMjkzLjk1MSAyMC4yMDk4IDI5Mi44NSAyMC42MjQyIDI5MS45OTMgMjEuMzc1MkMyOTEuMTM2IDIyLjEyNjEgMjkwLjU4IDIzLjE2MjYgMjkwLjQyOSAyNC4yOTIySDIyOS4zMkwyMDUuMDMxIC0wLjAwMDk2MTMwNEgyOS4zMzE1TDcuNDA2NjUgNzEuOTI5N0M2IDcxLjkyOTcgNS4yMzk2MiA3MS45NDcgNC4wNjAyNCA3Mi4xMDczQzIuODgwODYgNzIuMjY3NiAxLjgwNjQ5IDcyLjg3MDIgMS4wNTQ2NiA3My43OTNDMC4zMDI4MjYgNzQuNzE1OSAtMC4wNzAyODIgNzUuODkgMC4wMTA5NTU4IDc3LjA3NzdDMC4wOTIxOTM2IDc4LjI2NTMgMC42MjE2NzQgNzkuMzc3NyAxLjQ5MjE2IDgwLjE4OTVDMi4zNjI2NCA4MS4wMDE0IDMuNTA5MDYgODEuNDUyIDQuNjk5MjggODEuNDUwMkM1Ljg4OTUgODEuNDQ4NCA3LjAzNDU4IDgwLjk5NDIgNy45MDI1NiA4MC4xNzk3QzguNzcwNTQgNzkuMzY1MiA5LjI5NjU0IDc4LjI1MTIgOS4zNzQxMSA3Ny4wNjMzQzkuNDUxNjkgNzUuODc1NCA5LjA3NTA0IDczLjcwMjQgOC4zMjAzNyA3Mi43ODE5TDI5LjgzNjUgMS4yNDg0SDIwNC40ODdMMjI4Ljc3NyAyNS41NDE2SDI5MC40MjlDMjkwLjU1IDI2LjQzNzEgMjkwLjkyNiAyNy4yNzg5IDI5MS41MTIgMjcuOTY2M0MyOTIuMDk4IDI4LjY1MzggMjkyLjg3IDI5LjE1NzcgMjkzLjczNSAyOS40MThDMjk0LjYwMSAyOS42NzgzIDI5NS41MjIgMjkuNjgzOSAyOTYuMzkxIDI5LjQzNEMyOTcuMjU5IDI5LjE4NDIgMjk4LjAzNyAyOC42ODk2IDI5OC42MzIgMjguMDA5M0MyOTkuMjI2IDI3LjMyODkgMjk5LjYxMiAyNi40OTE3IDI5OS43NDQgMjUuNTk3N0MyOTkuODc1IDI0LjcwMzcgMjk5Ljc0NyAyMy43OTA4IDI5OS4zNzMgMjIuOTY4QzI5OSAyMi4xNDUyIDI5OC4zOTcgMjEuNDQ3NSAyOTcuNjM3IDIwLjk1ODFDMjk2Ljg3OCAyMC40Njg4IDI5NS45OTQgMjAuMjA4NiAyOTUuMDkgMjAuMjA4NloiIGZpbGw9IiM0QjY4ODQiLz4KPC9zdmc+Cg==');
				}
			}
			.third {
				margin-bottom: -165px;
				transform: translate(-200px, -60%);
			}
		}
		&--info {
			h3 {
				font-size: 25px;
				line-height: 35px;
				color: #65B9F4;
				position: relative;
				&::after {
					content: '';
					position: absolute;
					bottom: -10px;
					left: 0;
					width: 109px;
					height: 1px;
					background: #FF8B60;
				}
			}
			p {
				color: #F4F4F4;
				font-size: 20px;
				line-height: 28px;
				margin: 20px 0 30px;
				font-family: 'Inter', sans-serif;
				&:last-child {
					margin-bottom: 0;
				}
			}
		}
	}
}
</style>