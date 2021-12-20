<template>
	<section class="projects">
		<div class="projects__header">
			<h2>AI проекты<br>студентов</h2>
			<p>Наши студенты создали более <b>196</b> AI проектов.<br>Посмотрите некоторые из них</p>
		</div>
		<div class="projects__content">
			<button type="button" class="prev" @click="shift += 617" :disabled="shift >= 0" aria-label="Пролистать список назад"></button>
			<button type="button" class="next" @click="shift -= 617" :disabled="shift < -6700" aria-label="Пролистать список вперёд"></button>
			<div class="examples" :style="{ transform: `translate(${shift}px)` }">
				<figure class="examples__item" v-for="(project, idx) in projects" :key="idx">
					<img :src="project.src" :srcset="project.srcset" :aria-labelledby="idx">
					<figcaption :id="idx">{{ project.info }}</figcaption>
				</figure>
			</div>
		</div>
	</section>
</template>

<script>
import projects from '../assets/projects'

export default {
	name: 'Projects',
	data: () => ({
		projects: projects.list,
		shift: 0
	})
}
</script>

<style lang="scss" scoped>
.projects {
	background: #FFFFFF;
	font-family: 'Inter', sans-serif;
	&__header {
		display: flex;
		flex-wrap: wrap;
		align-items: center;
		padding-bottom: 0;
		b {
			color: #FF8B60;
		}
		p {
			border-left: 1px solid #65B9F4;
			padding-left: 10px;
			color: #383838;
		}
		h2 {
			font-size: 50px;
			line-height: 58px;
			font-weight: 400;
			font-family: 'Play', sans-serif;
		}
		> * {
			flex: 1 0 450px;
		}
	}
	&__content {
		button {
			cursor: pointer;
			width: 44px;
			height: 44px;
			border: none;
		}
		.prev {
			background: no-repeat center url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMzYiIGhlaWdodD0iMzQiIHZpZXdCb3g9IjAgMCAzNiAzNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggZD0iTTAuNDAwMDg2IDMuMTU3NjhMMTAuNzg1OSAxNi45OTkzTDAuNDAwMDg3IDMwLjg0MUMwLjA4ODQyMDYgMzEuMjUzNSAwLjAzMzQyMDQgMzEuODEyNyAwLjI3MTc1NCAzMi4yODAyQzAuNTAwOTIgMzIuNzQ3NyAwLjk3NzU4NyAzMy4wNDEgMS41MDAwOSAzMy4wNDFMMTIuNTAwMSAzMy4wNDFMMjMuNTAwMSAzMy4wNDFDMjMuOTMwOSAzMy4wNDEgMjQuMzQzNCAzMi44MzkzIDI0LjYwMDEgMzIuNDkxTDM1LjYwMDEgMTcuODI0M0MzNS43ODM0IDE3LjU3NjggMzUuODc1MSAxNy4yOTI3IDM1Ljg3NTEgMTYuOTk5M0MzNS44NzUxIDE2LjcwNiAzNS43ODM0IDE2LjQyMTggMzUuNjAwMSAxNi4xNzQzTDI0LjYwMDEgMS41MDc2OEMyNC4zNDM0IDEuMTU5MzQgMjMuOTMwOSAwLjk1NzY3OSAyMy41MDAxIDAuOTU3Njc5TDEyLjUwMDEgMC45NTc2NzlMMS41MDAwOSAwLjk1NzY4QzAuOTc3NTg2IDAuOTU3NjggMC41MDA5MTkgMS4yNTEwMSAwLjI3MTc1MiAxLjcxODUyQzAuMDMzNDE5MSAyLjE4NjAxIDAuMDg4NDE5NCAyLjc0NTE4IDAuNDAwMDg2IDMuMTU3NjhaTTIyLjgxMjYgMy43MDc2OEwzMi43ODU5IDE2Ljk5OTNMMjIuODEyNiAzMC4yOTFMMTUuMjUwMSAzMC4yOTFMMjQuNjAwMSAxNy44MjQzQzI0Ljc4MzQgMTcuNTc2OCAyNC44NzUxIDE3LjI5MjcgMjQuODc1MSAxNi45OTkzQzI0Ljg3NTEgMTYuNzA2IDI0Ljc4MzQgMTYuNDIxOCAyNC42MDAxIDE2LjE3NDNMMTUuMjUwMSAzLjcwNzY4TDIyLjgxMjYgMy43MDc2OFpNMTEuODEyNiAzLjcwNzY4TDIxLjc4NTkgMTYuOTk5M0wxMS44MTI2IDMwLjI5MUw0LjI1MDA5IDMwLjI5MUwxMy42MDAxIDE3LjgyNDNDMTMuOTY2OCAxNy4zMzg1IDEzLjk2NjggMTYuNjYwMiAxMy42MDAxIDE2LjE3NDNMNC4yNTAwOSAzLjcwNzY4TDExLjgxMjYgMy43MDc2OFoiIGZpbGw9IiNGRjhCNjAiLz4KPC9zdmc+Cg==');
			transform: rotateY(180deg);
			&:disabled {
				background: no-repeat center url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMzYiIGhlaWdodD0iMzQiIHZpZXdCb3g9IjAgMCAzNiAzNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggZD0iTTM1LjU5OTkgMzAuODQyM0wyNS4yMTQxIDE3LjAwMDdMMzUuNTk5OSAzLjE1ODk4QzM1LjkxMTYgMi43NDY0OCAzNS45NjY2IDIuMTg3MzIgMzUuNzI4MiAxLjcxOTgyQzM1LjQ5OTEgMS4yNTIzMiAzNS4wMjI0IDAuOTU4OTg0IDM0LjQ5OTkgMC45NTg5ODRMMjMuNDk5OSAwLjk1ODk4NEwxMi40OTk5IDAuOTU4OTg0QzEyLjA2OTEgMC45NTg5ODQgMTEuNjU2NiAxLjE2MDY1IDExLjM5OTkgMS41MDg5OEwwLjM5OTkwNiAxNi4xNzU3QzAuMjE2NTc2IDE2LjQyMzIgMC4xMjQ5MDggMTYuNzA3MyAwLjEyNDkwOCAxNy4wMDA3QzAuMTI0OTA4IDE3LjI5NCAwLjIxNjU3NiAxNy41NzgyIDAuMzk5OTA2IDE3LjgyNTdMMTEuMzk5OSAzMi40OTIzQzExLjY1NjYgMzIuODQwNyAxMi4wNjkxIDMzLjA0MjMgMTIuNDk5OSAzMy4wNDIzSDIzLjQ5OTlIMzQuNDk5OUMzNS4wMjI0IDMzLjA0MjMgMzUuNDk5MSAzMi43NDkgMzUuNzI4MiAzMi4yODE1QzM1Ljk2NjYgMzEuODE0IDM1LjkxMTYgMzEuMjU0OCAzNS41OTk5IDMwLjg0MjNaTTEzLjE4NzQgMzAuMjkyM0wzLjIxNDA3IDE3LjAwMDdMMTMuMTg3NCAzLjcwODk4TDIwLjc0OTkgMy43MDg5OEwxMS4zOTk5IDE2LjE3NTdDMTEuMjE2NiAxNi40MjMyIDExLjEyNDkgMTYuNzA3MyAxMS4xMjQ5IDE3LjAwMDdDMTEuMTI0OSAxNy4yOTQgMTEuMjE2NiAxNy41NzgyIDExLjM5OTkgMTcuODI1N0wyMC43NDk5IDMwLjI5MjNIMTMuMTg3NFpNMjQuMTg3NCAzMC4yOTIzTDE0LjIxNDEgMTcuMDAwN0wyNC4xODc0IDMuNzA4OThMMzEuNzQ5OSAzLjcwODk4TDIyLjM5OTkgMTYuMTc1N0MyMi4wMzMyIDE2LjY2MTUgMjIuMDMzMiAxNy4zMzk4IDIyLjM5OTkgMTcuODI1N0wzMS43NDk5IDMwLjI5MjNIMjQuMTg3NFoiIGZpbGw9IiNDNEM0QzQiLz4KPC9zdmc+Cg==');
				transform: rotateY(0);
			}
		}
		.next {
			margin-left: 30px;
			background: no-repeat center url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMzYiIGhlaWdodD0iMzQiIHZpZXdCb3g9IjAgMCAzNiAzNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggZD0iTTAuNDAwMDg2IDMuMTU3NjhMMTAuNzg1OSAxNi45OTkzTDAuNDAwMDg3IDMwLjg0MUMwLjA4ODQyMDYgMzEuMjUzNSAwLjAzMzQyMDQgMzEuODEyNyAwLjI3MTc1NCAzMi4yODAyQzAuNTAwOTIgMzIuNzQ3NyAwLjk3NzU4NyAzMy4wNDEgMS41MDAwOSAzMy4wNDFMMTIuNTAwMSAzMy4wNDFMMjMuNTAwMSAzMy4wNDFDMjMuOTMwOSAzMy4wNDEgMjQuMzQzNCAzMi44MzkzIDI0LjYwMDEgMzIuNDkxTDM1LjYwMDEgMTcuODI0M0MzNS43ODM0IDE3LjU3NjggMzUuODc1MSAxNy4yOTI3IDM1Ljg3NTEgMTYuOTk5M0MzNS44NzUxIDE2LjcwNiAzNS43ODM0IDE2LjQyMTggMzUuNjAwMSAxNi4xNzQzTDI0LjYwMDEgMS41MDc2OEMyNC4zNDM0IDEuMTU5MzQgMjMuOTMwOSAwLjk1NzY3OSAyMy41MDAxIDAuOTU3Njc5TDEyLjUwMDEgMC45NTc2NzlMMS41MDAwOSAwLjk1NzY4QzAuOTc3NTg2IDAuOTU3NjggMC41MDA5MTkgMS4yNTEwMSAwLjI3MTc1MiAxLjcxODUyQzAuMDMzNDE5MSAyLjE4NjAxIDAuMDg4NDE5NCAyLjc0NTE4IDAuNDAwMDg2IDMuMTU3NjhaTTIyLjgxMjYgMy43MDc2OEwzMi43ODU5IDE2Ljk5OTNMMjIuODEyNiAzMC4yOTFMMTUuMjUwMSAzMC4yOTFMMjQuNjAwMSAxNy44MjQzQzI0Ljc4MzQgMTcuNTc2OCAyNC44NzUxIDE3LjI5MjcgMjQuODc1MSAxNi45OTkzQzI0Ljg3NTEgMTYuNzA2IDI0Ljc4MzQgMTYuNDIxOCAyNC42MDAxIDE2LjE3NDNMMTUuMjUwMSAzLjcwNzY4TDIyLjgxMjYgMy43MDc2OFpNMTEuODEyNiAzLjcwNzY4TDIxLjc4NTkgMTYuOTk5M0wxMS44MTI2IDMwLjI5MUw0LjI1MDA5IDMwLjI5MUwxMy42MDAxIDE3LjgyNDNDMTMuOTY2OCAxNy4zMzg1IDEzLjk2NjggMTYuNjYwMiAxMy42MDAxIDE2LjE3NDNMNC4yNTAwOSAzLjcwNzY4TDExLjgxMjYgMy43MDc2OFoiIGZpbGw9IiNGRjhCNjAiLz4KPC9zdmc+Cg==');
			&:disabled {
				background: no-repeat center url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMzYiIGhlaWdodD0iMzQiIHZpZXdCb3g9IjAgMCAzNiAzNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggZD0iTTM1LjU5OTkgMzAuODQyM0wyNS4yMTQxIDE3LjAwMDdMMzUuNTk5OSAzLjE1ODk4QzM1LjkxMTYgMi43NDY0OCAzNS45NjY2IDIuMTg3MzIgMzUuNzI4MiAxLjcxOTgyQzM1LjQ5OTEgMS4yNTIzMiAzNS4wMjI0IDAuOTU4OTg0IDM0LjQ5OTkgMC45NTg5ODRMMjMuNDk5OSAwLjk1ODk4NEwxMi40OTk5IDAuOTU4OTg0QzEyLjA2OTEgMC45NTg5ODQgMTEuNjU2NiAxLjE2MDY1IDExLjM5OTkgMS41MDg5OEwwLjM5OTkwNiAxNi4xNzU3QzAuMjE2NTc2IDE2LjQyMzIgMC4xMjQ5MDggMTYuNzA3MyAwLjEyNDkwOCAxNy4wMDA3QzAuMTI0OTA4IDE3LjI5NCAwLjIxNjU3NiAxNy41NzgyIDAuMzk5OTA2IDE3LjgyNTdMMTEuMzk5OSAzMi40OTIzQzExLjY1NjYgMzIuODQwNyAxMi4wNjkxIDMzLjA0MjMgMTIuNDk5OSAzMy4wNDIzSDIzLjQ5OTlIMzQuNDk5OUMzNS4wMjI0IDMzLjA0MjMgMzUuNDk5MSAzMi43NDkgMzUuNzI4MiAzMi4yODE1QzM1Ljk2NjYgMzEuODE0IDM1LjkxMTYgMzEuMjU0OCAzNS41OTk5IDMwLjg0MjNaTTEzLjE4NzQgMzAuMjkyM0wzLjIxNDA3IDE3LjAwMDdMMTMuMTg3NCAzLjcwODk4TDIwLjc0OTkgMy43MDg5OEwxMS4zOTk5IDE2LjE3NTdDMTEuMjE2NiAxNi40MjMyIDExLjEyNDkgMTYuNzA3MyAxMS4xMjQ5IDE3LjAwMDdDMTEuMTI0OSAxNy4yOTQgMTEuMjE2NiAxNy41NzgyIDExLjM5OTkgMTcuODI1N0wyMC43NDk5IDMwLjI5MjNIMTMuMTg3NFpNMjQuMTg3NCAzMC4yOTIzTDE0LjIxNDEgMTcuMDAwN0wyNC4xODc0IDMuNzA4OThMMzEuNzQ5OSAzLjcwODk4TDIyLjM5OTkgMTYuMTc1N0MyMi4wMzMyIDE2LjY2MTUgMjIuMDMzMiAxNy4zMzk4IDIyLjM5OTkgMTcuODI1N0wzMS43NDk5IDMwLjI5MjNIMjQuMTg3NFoiIGZpbGw9IiNDNEM0QzQiLz4KPC9zdmc+Cg==');
				transform: rotateY(180deg);
			}
		}
		.examples {
			margin-top: 34px;
			display: flex;
			gap: 54px;
			transform: translateX(0);
			transition-duration: 500ms;
			img {
				border-radius: 4px;
				border: 1px solid #65B9F4;
			}
			figcaption {
				font-weight: 600;
				color: #3F5168;
				margin-top: 25px;
			}
		}
	}
}
</style>