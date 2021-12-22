<template>
	<div class="options">
		<label class="radio" v-for="(option, idx) in options" :key="idx">
			<input type="radio" class="radio__input" :name="options[0]" :value="option" @input="handleInput" :checked="selected === option">
			<span class="radio__custom"></span>
			{{ option }}
		</label>
	</div>
</template>

<script>
export default {
	name: 'input-radio',
	props: ['options', 'selected'],
	methods: {
		handleInput(e) {
			this.$emit('input', e.target.value)
		}
	}
}
</script>

<style lang="scss" scoped>
.options {
	display: flex;
	flex-direction: column;
	gap: 10px;
	.radio {
		color: #dfe6ed;
		cursor: pointer;
		padding-left: 1em;
		vertical-align: middle;
		&__input {
			appearance: none;
			&:checked + .radio__custom::after {
				content: '';
				background: #ff9e5e;
				display: block;
				width: 10px;
				height: 10px;
				transform: translate(2px, 2px);
				border-radius: 50%;
			}
		}
		&__custom {
			position: absolute;
			margin-left: -1em;
			margin-top: .1em;
			width: 1em;
			height: 1em;
			border: 2px solid #ff9e5e;
			border-radius: 50%;
		}
	}
}

@media (max-width: 550px) {
	.options .radio__input:checked + .radio__custom::after {
		width: .5em;
		height: .5em;
		transform: translate(1.5px, 1.5px);
	}
	.options {
		.radio {
			font-size: 15px;
		}
	}
}
</style>