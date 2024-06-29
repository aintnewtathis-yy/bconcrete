<script>
	import { onMount } from 'svelte';
	import { Splide, SplideSlide, SplideTrack } from '@splidejs/svelte-splide';
	import '@splidejs/svelte-splide/css/core';

	let childWidth;

	onMount(() => {
		childWidth = document.querySelector('.container').offsetWidth / 100 * 40
		console.log(childWidth)
	})
</script>

<section class="news-row-section --margin-bottom">
	<div class="container">
		<div class="news-row">
			<p class="--text-m">Медиа</p>
			<Splide
				options={{
					fixedWidth: `${childWidth}px`,
					arrows: false,
					gap: '20px',
					drag   : 'free',
					snap: true
				}}
				aria-label="My Favorite Images"
				class="news-row-slider-wrap"
			>
				<SplideSlide class="news-row-slider-element">
					<img src="/media.webp" alt="" />
					<h5>Проведите эту зиму в уюте и комфорте вместе c коллецией Hygge</h5>
					<p>05 декабря 2023</p>
				</SplideSlide>
				<SplideSlide class="news-row-slider-element">
					<img src="/media.webp" alt="" />
					<h5>Проведите эту зиму в уюте и комфорте вместе c коллецией Hygge</h5>
					<p>05 декабря 2023</p>
				</SplideSlide>
				<SplideSlide class="news-row-slider-element">
					<img src="/media.webp" alt="" />
					<h5>Проведите эту зиму в уюте и комфорте вместе c коллецией Hygge</h5>
					<p>05 декабря 2023</p>
				</SplideSlide>
				<SplideSlide class="news-row-slider-element">
					<img src="/media.webp" alt="" />
					<h5>Проведите эту зиму в уюте и комфорте вместе c коллецией Hygge</h5>
					<p>05 декабря 2023</p>
				</SplideSlide>
				<SplideSlide class="news-row-slider-element">
					<img src="/media.webp" alt="" />
					<h5>Проведите эту зиму в уюте и комфорте вместе c коллецией Hygge</h5>
					<p>05 декабря 2023</p>
				</SplideSlide>
			</Splide>
		</div>
	</div>
</section>

<style lang="scss">
	.news-row {
		display: flex;
		flex-direction: column;
		gap: 20px;

		& > p {
			padding-left: 30px;
		}

		&-slider {
			display: flex;
			gap: 20px;
		}
	}

	:global(.news-row-slider-element) {
		display: flex;
		flex-direction: column;
		gap: 20px;

		img {
			border-radius: 10px;
			object-fit: cover;
		}

		h5 {
			font-size: 25px;
			text-wrap: balance;
		}
		p {
			color: var(--gray-color);
			font-size: 14px;
		}
	}
	:global(.news-row-slider-wrap) {
		overflow: hidden;
	}
</style>
