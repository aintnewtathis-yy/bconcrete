<script>
</script>

<section class="variety-section --margin-bottom">
	<div class="container">
		<div class="variety">
			<div class="variety-info">
				<h4 class="--text-l">Широкий спектр <br />дизайнерских решений</h4>
				<p>Бесплатная консультация и забота о каждом клиенте</p>
				<a href="#" class="btn-main btn-gray"> Перейти в каталог </a>
			</div>

			<div class="variety-projects">
				<div class="variety-projects-sidecolumn">
					<div>
						<img src="/variety.png" alt="" />
						<img src="/variety2.png" alt="" />
					</div>
					<img src="/variety3.png" alt="" />
				</div>
				<div class="variety-projects-centercolumn">
					<img src="/variety2.png" alt="" />
				</div>
				<div class="variety-projects-sidecolumn">
					<div>
						<img src="/variety.png" alt="" />
						<img src="/variety3.png" alt="" />
					</div>
					<img src="/variety2.png" alt="" />
				</div>
			</div>
		</div>
	</div>
</section>

<style lang="scss">
	.variety {
		display: flex;
		flex-direction: column;
		gap: 20px;

		&-info {
			display: flex;
			flex-direction: column;
			align-items: center;
			gap: 20px;

			h4 {
				text-align: center;
			}
			p {
				padding-top: 40px;
				text-align: center;
				color: var(--gray-color);
				font-size: 16px;
			}
		}

		&-projects {
			display: grid;
			grid-template-columns: 1fr 35% 1fr;
			gap: 20px;

			img {
				height: 100%;
				object-fit: cover;
				border-radius: 10px;
			}

			&-sidecolumn {
				display: flex;
				flex-direction: column;
				gap: 20px;

				&:first-child {
					div {
						display: grid;
						grid-template-columns: 1fr 66%;
						gap: 20px;
						align-items: end;

						img {
							aspect-ratio: 1/3.2;
						}

						img:last-child {
							height: calc(100% - 40px);
							margin-top: 40px;
							aspect-ratio: 1/1.35;
						}
					}
				}
				&:last-child {
					div {
						display: grid;
						grid-template-columns: 66% 1fr;
						gap: 20px;
						align-items: end;

						img {
							aspect-ratio: 1/3.2;
						}

						img:first-child {
							height: calc(100% - 40px);
							margin-top: 40px;
							aspect-ratio: 1/1.35;
						}
					}
				}
			}
			&-centercolumn {
				img {
                    height: calc(100% - 74px);
					margin-top: 74px;
				}
			}
		}
	}
</style>
