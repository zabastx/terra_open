<template>
	<section class="partners">
		<div class="partners__content">
			<div class="partners__content--header">
				<h2>Нам доверяют <br>компании</h2>
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
			flex-wrap: wrap;
			h2 {
				font-size: 50px;
				font-weight: 400;
			}
			p {
				color: #383838;
				font-size: 20px;
				line-height: 1.4em;
				border-left: 1px solid #65B9F4;
				padding-left: 10px;
			}
			> * {
				flex: 1 1 400px;
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

@media (max-width: 1240px) {
	.partners {
		&__content {
			padding: 100px 20px 100px 40px;
			&--companies {
				.img-wrapper {
					padding: 35px 0;
					padding-right: 20px;
					img {
						max-width: 150px;
					}
				}
			}
			&--header {
				h2 {
					font-size: 40px;
				}
				p {
					font-size: 18px;
				}
			}
		}
	}
}

@media (max-width: 860px) {
	.partners {
		&__content {
			&--header {
				h2 {
					font-size: 30px;
					br {
						display: none;
					}
				}
				p {
					font-size: 16px;
					margin-top: 45px;
					max-width: 575px;
				}
			}
		}
	}
}

@media (max-width: 550px) {
	.partners {
		&__content {
			padding: 100px 10px;
			&--companies {
				.img-wrapper {
					padding: 22px 0;
					padding-right: 15px;
					img {
						max-width: 85px;
					}
				}
			}
		}
	}
}
</style>