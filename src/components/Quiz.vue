<template>
	<form class="form" @submit.prevent="submit">
		<div class="form__progress">
			<div class="form__progress--bar" v-for="idx in 6" :key="idx">
				<div v-show="idx < stage"></div>
			</div>
		</div>
		<fieldset class="form__content">
			<legend class="form__title">{{ titles[stage-1] }}</legend>
			<InputRadio class="form__options" v-if="!finalStage" :options="options[stage]" @input="handleInput" :key="stage" :selected="answers[stage]" />
			<RegForm v-else class="form__register" @input="regInput" />
		</fieldset>
		<div class="form__btns">
			<button type="button" class="btn back" v-show="stage > 1" :disabled="!(stage > 1)" @click="stage--" aria-label="Назад"></button>
			<button type="button" class="btn forward" v-show="stage < 6" :disabled="!(stage < 6)" @click="stage++" aria-label="Вперёд"></button>
			<button type="button" class="btn last" v-show="stage === 6" :disabled="!(stage === 6)" @click="stage++" aria-label="К последнему"></button>
			<button type="submit" class="btn submit" v-show="finalStage" :disabled="!finalStage" aria-label="Зарегистрироваться"></button>
		</div>
	</form>
</template>

<script>
import options from '../assets/options'
import InputRadio from './InputRadio.vue'
import RegForm from './RegForm.vue'

export default {
	name: 'Quiz',
	components: {
		InputRadio,
		RegForm
	},
	data: () => ({
		answers: {
			1: options[1][0],
			2: options[2][0],
			3: options[3][0],
			4: options[4][0],
			5: options[5][0],
			6: options[6][0],
			name: '',
			email: '',
			tel: ''
		},
		options,
		titles: [
			'Из какой вы страны?',
			'Сколько вам лет?',
			'В какой сфере сейчас работаете?',
			'Ваш средний доход в месяц',
			'Рассматриваете ли в перспективе платное обучение профессии Разработчик Искусственного Интеллекта?',
			'Сколько времени готовы выделить на обучение в неделю?',
			'Зарегистрироваться'
		],
		stage: 1
	}),
	computed: {
		btnText() {
			if (this.stage === 6) return 'К последнему'
			return 'Вперёд'
		},
		finalStage() {
			return this.stage === 7
		}
	},
	methods: {
		submit() {
			window.location.href = 'https://neural-university.ru/thank_you'
		},
		handleInput(input) {
			this.answers[this.stage] = input
		},
		regInput(e) {
			this.answers[e.type] = e.value
		}
	}
}
</script>

<style lang="scss" scoped>
.form {
	width: 100%;
	max-width: 600px;
	position: relative;
	display: flex;
	flex-direction: column;
	padding: 8px 0;
	gap: 30px;
	height: 509px;
	background: no-repeat url('../assets/form.svg');
	background-size: 100% 100%;
	&__content {
		flex-grow: 1;
		padding: 0 40px;
		border: none;
	}
	&__title {
		color: #dfe6ed;
		font-size: 24px;
		margin-bottom: 30px;
	}
	&__progress {
		height: 8px;
		display: flex;
		gap: 5px;
		margin: 0 13% 0 7%;
		&--bar {
			border: 1px solid #65B9F4;
			flex-grow: 1;
			div {
				background: #65B9F4;
				height: 100%;
			}
		}
	}
	img {
		width: 100%;
		display: block;
		position: absolute;
		top: 0;
		left: 0;
		height: 100%;
	}
	&__btns {
		margin: auto;
		margin-right: 10px;
		display: flex;
		justify-content: flex-end;
	}
	.btn {
		border: none;
		background: none;
		font-size: 100%;
		font-family: inherit;
		flex: 1 0 240px;
		height: 65px;
		padding: 0;
		cursor: pointer;
		&.forward {
			background: no-repeat url('../assets/btn-forward.svg');
		}
		&.back {
			background: no-repeat url('../assets/btn-back.svg');
		}
		&.last {
			background: no-repeat url('../assets/btn-last.svg');
		}
		&.submit {
			font-size: 16px;
			background: no-repeat url('../assets/btn-reg.svg');
		}
	}
}

@media (max-width: 640px) {
	.form {
		background: no-repeat url('data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiPz4gPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHByZXNlcnZlQXNwZWN0UmF0aW89Im5vbmUiIHdpZHRoPSIzMDEiIGhlaWdodD0iMzcyIiB2aWV3Qm94PSIwIDAgMzAxIDM3MiIgZmlsbD0ibm9uZSI+IDxwYXRoIGQ9Ik0wLjUgMjcuMTc5NEMwLjUgMjYuNDgwMyAwLjcwOTM1NSAyNS43OTczIDEuMTAxMDkgMjUuMjE4MkwxNi43ODI3IDIuMDM4OEwxNi4zNjg2IDEuNzU4NjJMMTYuNzgyNyAyLjAzODc5QzE3LjQzMzcgMS4wNzY1MSAxOC41MTk4IDAuNSAxOS42ODE2IDAuNUgyNjAuNTcyQzI2MS42OTkgMC41IDI2Mi43NTYgMS4wNDE5NCAyNjMuNDE0IDEuOTU2MThMMjk5Ljg0MSA1Mi41OTcxQzMwMC4yNyA1My4xOTI1IDMwMC41IDUzLjkwNzQgMzAwLjUgNTQuNjQwOVYzNjhDMzAwLjUgMzY5LjkzMyAyOTguOTMzIDM3MS41IDI5NyAzNzEuNUgxMjEuNjU0SDRDMi4wNjcwMSAzNzEuNSAwLjUgMzY5LjkzMyAwLjUgMzY4VjI3LjE3OTRaIiBmaWxsPSIjMkI1Mjc4IiBmaWxsLW9wYWNpdHk9IjAuMiIgc3Ryb2tlPSIjNjVCOUY0Ij48L3BhdGg+IDxwYXRoIGQ9Ik0zMDAgMzguOTU4NUwyNzIuNDggMUgyOTYuNUMyOTguNDMzIDEgMzAwIDIuNTY3IDMwMCA0LjVWMzguOTU4NVoiIGZpbGw9IiMyQjUyNzgiIHN0cm9rZT0iIzY1QjlGNCI+PC9wYXRoPiA8L3N2Zz4g');
		background-size: 100% 100%;
		&__btns {
			justify-content: center;
			margin: auto;
			transform: scale(80%);
		}
	}
}

@media (max-width: 550px) {
	.form__content {
		padding: 0 20px;
	}
}
</style>