<script>
	import { onMount } from 'svelte';

	let links;

	onMount(() => {
		links = document.querySelectorAll('.categories a');

		links.forEach((link) => {
			link.addEventListener('mouseover', () => {
				link.classList.add('hovered');
			});
			link.addEventListener('mouseleave', () => {
				link.classList.remove('hovered');
			});
		});
	});
</script>

<section class="categories-section --margin-bottom">
	<div class="container">
		<div class="categories">
			<a href="#">
				<img src="/kashpo.webp" alt="" />
				<p>Раковины и мойки</p>
			</a>
			<a href="#">
				<img src="/kashpo2.webp" alt="" />
				<p>Столешницы и столы</p>
			</a>
			<a href="#">
				<img src="/kashpo3.webp" alt="" />
				<p>Кашпо и вазоны</p>
			</a>
			<a href="#">
				<img src="/kashpo4.webp" alt="" />
				<p>Панели и плитка</p>
			</a>
			<a href="#">
				<img src="/kashpo5.webp" alt="" />
				<p>Торговое оборудование</p>
			</a>
			<a href="#">
				<img src="/kashpo6.webp" alt="" />
				<p>Стойки-ресепшн</p>
			</a>
		</div>
	</div>
</section>

<style lang="scss">
	.categories {
		display: grid;
		grid-template-columns: 1fr 1fr 1fr 1fr 1fr 1fr;
		gap: 20px;

		&:global(:has(.hovered)) {
			a {
				p {
					color: var(--gray-color);
				}
			}
		}

		a {
			display: flex;
			flex-direction: column;
			gap: 20px;

			&:global(.hovered) {
				p{
                    color: var(--text-color) !important;
                }
			}

			img {
				border-radius: 8px;
				object-fit: cover;
			}

			p {
				color: var(--text-color);
				text-align: center;
			}
		}
	}
</style>
