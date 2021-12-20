<template>
	<section class="partners">
		<div class="partners__content">
			<div class="partners__content--header">
				<h2>Нам доверяют<br>компании</h2>
				<p>Более 500 компаний обратились к нам, чтобы обучить своих разработчиков.<br>
					Более 200 компаний обратились к нам, чтобы нанять наших выпускников в штат или на проект.
				</p>
			</div>
			<div class="partners__content--companies">
				<div class="img-wrapper" v-for="(item, idx) in companies.list" :key="idx">
					<img :src="item.src" :alt="item.alt" :width="item.width">
				</div>
			</div>
		</div>
	</section>
</template>

<script>
import companies from '../assets/companies'

export default {
	name: 'Partners',
	data: () => ({
		companies
	})
}
</script>

<style lang="scss" scoped>
.partners {
	background: #F6F6F6;
	&__content {
		&--header {
			display: flex;
			margin-bottom: 50px;
			h2 {
				font-size: 50px;
				font-weight: 400;
			}
			p {
				color: #383838;
				font-size: 20px;
				line-height: 28px;
				border-left: 1px solid #65B9F4;
				padding-left: 10px;
			}
			> * {
				flex: 1 0 450px;
			}
		}
		&--companies {
			display: flex;
			flex-flow: row wrap;
  		align-items: stretch;
			.img-wrapper {
				border-bottom: 1px solid rgba(101, 185, 244, 0.4);
				padding: 50px 0;
				padding-right: 40px;
				flex-grow: 1;
				display: flex;
				align-items: center;
				justify-content: center;
				&:last-child {
					padding-right: 0;
				}
			}
		}
	}
}
</style>