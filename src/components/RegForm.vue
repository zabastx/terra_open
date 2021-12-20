<template>
	<div class="reg">
		<label class="label">
			<span>Имя</span>
			<input type="text" placeholder="Александр" required @input="input('name', $event)">
		</label>
		<label class="label">
			<span>Email</span>
			<input type="email" placeholder="Alex@gmail.com" required @input="input('email', $event)">
		</label>
		<label class="label">
			<span>Телефон</span>
			<input type="tel" placeholder="+7 900 000 00 00" required @input="input('tel', $event)">
		</label>
	</div>
</template>

<script>
export default {
	name: 'reg-form',
	methods: {
		update(e) {
			this.$emit('update', { tel: e.phoneNumber, code: e.countryCode })
		},
		input(type, e) {
			this.$emit('input', { type, value: e.target.value })
		}
	}
}
</script>

<style lang="scss" scoped>
.reg {
	display: flex;
	flex-direction: column;
	gap: 20px;
	.label {
		display: flex;
		flex-direction: column;
		color: #a7bed3;
		font-size: 18px;
		gap: 10px;
		input {
			height: 30px;
			background: none;
			border: none;
			color: inherit;
			font: inherit;
			font-size: 14px;
			border-bottom: 1px solid #ff9e5e;
		}
	}
}
</style>