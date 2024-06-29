<script>
	export let minititle
	export let largeProduct
	export let products
</script>

<section class="mini-catalog-section">
	<div class="container">
		<div class="mini-catalog --margin-bottom">
			<p class="--text-m">{minititle}</p>
			<div class="mini-catalog-grid" data-large-product={largeProduct}>
				{#each products as product}
					<a href={product.url} class="product-card">
						<img src={product.image} alt="" />
						<div class="colors">
                            {#each product.colors as color}
                                <div class="colors-element" style="background-color: {color};"></div>
                            {/each}
						</div>
						<div class="product-card-info">
							<h3 class="product-card-info-title">{product.title}</h3>
							<h3 class="product-card-info-price">{product.price} RUB</h3>
						</div>
						<p class="product-card-desc">{product.desc}</p>
					</a>
				{/each}
			</div>
		</div>
	</div>
</section>

<style lang="scss">
	.mini-catalog {
		display: flex;
		flex-direction: column;
		gap: 20px;

		& > p {
			padding-left: 30px;
		}

		.mini-catalog-grid {
			display: grid;
			grid-template-columns: 1fr 1fr 1fr;
			grid-template-rows: 1fr 1fr;
			gap: 20px;

			&[data-large-product=true] {
				.product-card:first-child {
					grid-column: 1/3;
					grid-row: 1/3;

					img {
						height: 100%;
					}
				}
			}

			.product-card {
				display: flex;
				flex-direction: column;
				gap: 4px;

				.colors {
					display: flex;
					padding-top: 6px;

					&-element {
						width: 18px;
						height: 18px;
						border-radius: 100%;

						&:not(:first-child){
                            margin-left: -7px;
                        }
					}
				}

				img {
					object-fit: cover;
					border-radius: 10px;
				}

				&-info {
					display: flex;
					justify-content: space-between;
					gap: 30px;
					padding-top: 3px;

					&-title {
						font-size: 18px;
					}
					&-price {
						font-size: 18px;
					}
				}
				&-desc {
					font-size: 14px;
					color: var(--gray-color);
				}
			}
		}
	}
</style>
