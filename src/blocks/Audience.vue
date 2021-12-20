<template>
	<section class="audience">
		<div class="audience__content">
			<div class="audience__content--left">
				<h2>Для кого этот курс</h2>
				<p>Сегодня люди очень разных профессий, возраста и опыта интересуются искусственным интеллектом</p>
			</div>
			<div class="audience__content--right">
				<div class="grid">
					<b>20%</b>
					<h3>Программисты</h3>
					<p class="underline">Java, C#, C/C++, Php, Python, 1C и другие</p>
				</div>
				<div class="grid linethrough">
					<b>20%</b>
					<h3>Технические специалисты</h3>
					<p class="underline">Инженеры, тестировщики, аналитики, сис.админы и другие</p>
				</div>
				<div class="grid decoration">
					<b>20%</b>
					<h3>Гуманитарии</h3>
					<p class="underline">Врачи, дизайнеры, юристы, репетиторы, прорабы и другие</p>
				</div>
				<div class="grid decoration2">
					<b>20%</b>
					<h3>Предприниматели и руководители</h3>
					<p class="underline">Владельцы бизнеса, директора, руководители отделов и другие</p>
				</div>
				<div class="grid">
					<b>20%</b>
					<h3>Другие</h3>
					<p>Школьники, пенсионеры, преподаватели и другие</p>
				</div>
			</div>
		</div>
	</section>
</template>

<script>
export default {
	name: 'Audience'
}
</script>

<style lang="scss" scoped>
.audience {
	background: #E4E4E4;
	&__content {
		display: flex;
		flex-wrap: wrap;
		> * {
			flex: 1 0 450px;
			max-width: 600px;
			margin: 0 auto;
		}
		h2 {
			font-size: 50px;
			line-height: 58px;
			font-weight: 400;
		}
		p {
			font-family: 'Inter', sans-serif;
			font-size: 20px;
			line-height: 28px;
		}
		&--left p {
			color: #383838;
			margin-top: 50px;
			max-width: 500px;
		}
		&--right {
			border-left: 3px solid #F6F6F6;
			.grid {
				display: grid;
				grid-template-rows: min-content 1fr;
				grid-template-columns: 135px 1fr;
				row-gap: 10px;
				column-gap: 30px;
				font-size: 20px;
				color: #4A4A4A;
				padding: 25px 0;
				position: relative;
				b {
					grid-row: 1 / 3;
					align-self: center;
					text-align: center;
					font-size: 30px;
					color: #FF8B60;
				}
				h3 {
					font-size: 25px;
					line-height: 35px;
					color: #30668B;
				}
				.underline::after {
					content: '';
					position: absolute;
					top: 100%;
					left: 0;
					height: 2px;
					width: 135px;
					background: #F6F6F6;
				}
				&.linethrough::after {
					content: '';
					position: absolute;
					top: 100%;
					height: 2px;
					right: 0;
					width: 100vw;
					background: #F6F6F6;
				}
				&.decoration::after {
					content: '';
					position: absolute;
					top: calc(100% - 9px);
					height: 20px;
					right: 211px;
					width: 554px;
					background: no-repeat 0 url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTkiIGhlaWdodD0iMTkiIHZpZXdCb3g9IjAgMCAxOSAxOSIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHJlY3Qgd2lkdGg9IjE5IiBoZWlnaHQ9IjE5IiByeD0iOS41IiBmaWxsPSJ3aGl0ZSIvPgo8L3N2Zz4K'),
					no-repeat center url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNTU0IiBoZWlnaHQ9IjIiIHZpZXdCb3g9IjAgMCA1NTQgMiIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggZD0iTTAgMEg1NTRWMkgwVjBaIiBmaWxsPSIjRjZGNkY2Ii8+Cjwvc3ZnPgo=');
				}
				&.decoration::before {
					content: '';
					position: absolute;
					left: -5px;
					bottom: 0;
					height: 15px;
					width: 10px;
					background: #E4E4E4;
				}
				&.decoration2::before {
					content: '';
					position: absolute;
					left: -5px;
					top: 2px;
					height: 15px;
					width: 10px;
					background: #E4E4E4;
				}
				&.decoration2::after {
					content: '';
					position: absolute;
					right: 100%;
					top: 10px;
					height: 14px;
					width: 117px;
					background: no-repeat 0 url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTQiIGhlaWdodD0iMTQiIHZpZXdCb3g9IjAgMCAxNCAxNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHJlY3Qgd2lkdGg9IjE0IiBoZWlnaHQ9IjE0IiByeD0iNyIgZmlsbD0id2hpdGUiLz4KPC9zdmc+Cg=='),
					no-repeat center url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTE3IiBoZWlnaHQ9IjIiIHZpZXdCb3g9IjAgMCAxMTcgMiIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggZD0iTTAgMEgxMTdWMkgwVjBaIiBmaWxsPSIjRjZGNkY2Ii8+Cjwvc3ZnPgo=');
				}
			}
		}
	}
}
</style>