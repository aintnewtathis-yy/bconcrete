<script>
	import { onMount } from 'svelte';

	const slides = [
		{
			pretitle: 'Столешница Wegner CH07 Shell',
			title: 'Проведите эту зиму в уюте и комфорте c коллецией Hygge',
			url: '#url',
			image: '/hero-bg.png'
		},
		{
			pretitle: 'Столешница Wegner CH07 Shell 2',
			title: 'Проведите эту зиму в уюте и комфорте c коллецией Hygge',
			url: '#url',
			image: '/hero-bg2.png'
		},
		{
			pretitle: 'Столешница Wegner CH07 Shell 3',
			title: 'Проведите эту зиму в уюте и комфорте c коллецией Hygge',
			url: '#url',
			image: '/hero-bg.png'
		},
		{
			pretitle: 'Столешница Wegner CH07 Shell 4',
			title: 'Проведите эту зиму в уюте и комфорте c коллецией Hygge',
			url: '#url',
			image: '/hero-bg2.png'
		}
	];

	$: backImage = 0
	let infos;
	let bgs;

	function increment() {
		if (backImage < slides.length - 1) {
			infos[backImage].classList.remove('visible');
			backImage += 1;
            bgs[backImage].classList.add('jpeged');
			setTimeout(() => {
				infos[backImage].classList.add('visible');
			}, 400);

			for (let i = 0; i < infos.length - 1; i++) {
				infos[i].classList.remove('next');
				infos[i].classList.remove('prev');
				bgs[i].classList.remove('prev');
				bgs[i].classList.remove('next');
			}

			infos[backImage].nextElementSibling?.classList.add('next');
			infos[backImage].previousElementSibling?.classList.add('prev');
			bgs[backImage].nextElementSibling?.classList.add('next');
			bgs[backImage].previousElementSibling?.classList.add('prev');
		}
	}

	function decrement() {
		if (backImage > 0) {
			bgs[backImage].classList.remove('jpeged');
			infos[backImage].classList.remove('visible');
			backImage -= 1;
			setTimeout(() => {
				infos[backImage].classList.add('visible');
				bgs[backImage].classList.add('jpeged');
			}, 400);

			for (let i = 0; i < infos.length - 1; i++) {
				infos[i].classList.remove('next');
				infos[i].classList.remove('prev');
				bgs[i].classList.remove('prev');
				bgs[i].classList.remove('next');
			}

			infos[backImage].nextElementSibling?.classList.add('next');
			infos[backImage].previousElementSibling?.classList.add('prev');
		}
	}

	onMount(() => {
		infos = document.querySelectorAll('.hero-info');
		bgs = document.querySelectorAll('.hero-section-bg');
	});
</script>

<section class="hero-section --margin-bottom">
	{#each slides as slide, i}
		<div class="hero-section-bg" class:jpeged={i == 0}>
            <img src={slide.image} alt="">
        </div>
	{/each}
	<div class="container">
		<div class="hero">
			<div>
				{#each slides as slide, i}
					<div
						class="hero-info"
						class:active={i == backImage}
						class:visible={i == 0}
					>
						<p>{slide.pretitle}</p>
						<h2 class="--text-l">{slide.title}</h2>

						<a href={slide.url} class="btn-main"> Перейти в каталог </a>
					</div>
				{/each}
			</div>
			<div class="handles">
				<div class="handles-pagination">
					{#each slides as _, i}
						<div class:active={i == backImage}></div>
					{/each}
				</div>
				<div class="handles-controls">
					<button on:click={decrement} disabled={backImage == 0}>
						<svg
							width="71"
							height="14"
							viewBox="0 0 71 14"
							fill="none"
							xmlns="http://www.w3.org/2000/svg"
						>
							<path
								d="M0.398956 6.39896C0.0670166 6.7309 0.0670166 7.2691 0.398956 7.60104L5.80833 13.0104C6.14027 13.3424 6.67846 13.3424 7.01041 13.0104C7.34235 12.6785 7.34235 12.1403 7.01041 11.8083L2.20208 7L7.01041 2.19167C7.34235 1.85973 7.34235 1.32154 7.01041 0.989592C6.67846 0.657647 6.14027 0.657647 5.80833 0.989592L0.398956 6.39896ZM71 6.15L1 6.15V7.85L71 7.85V6.15Z"
								fill="white"
							/>
						</svg>
					</button>

					<button on:click={increment} disabled={backImage > infos?.length - 2}>
						<svg
							width="71"
							height="14"
							viewBox="0 0 71 14"
							fill="none"
							xmlns="http://www.w3.org/2000/svg"
						>
							<path
								d="M0.398956 6.39896C0.0670166 6.7309 0.0670166 7.2691 0.398956 7.60104L5.80833 13.0104C6.14027 13.3424 6.67846 13.3424 7.01041 13.0104C7.34235 12.6785 7.34235 12.1403 7.01041 11.8083L2.20208 7L7.01041 2.19167C7.34235 1.85973 7.34235 1.32154 7.01041 0.989592C6.67846 0.657647 6.14027 0.657647 5.80833 0.989592L0.398956 6.39896ZM71 6.15L1 6.15V7.85L71 7.85V6.15Z"
								fill="white"
							/>
						</svg>
					</button>
				</div>
			</div>
		</div>
	</div>
</section>

<style lang="scss">
	.hero {
		display: flex;
		flex-direction: column;
		gap: 90px;
		padding-bottom: 125px;
		justify-content: flex-end;
		height: 100%;

		&-section {
			min-height: 100dvh;
			height: 100dvh;
			background-position: center center;
			background-repeat: no-repeat;
			background-size: cover;

			&-bg {
				position: absolute;
				width: 100%;
				height: 100%;
				top: 0;
				background-position: center center;
				background-size: cover;
				background-repeat: no-repeat;
				width: 0%;
                overflow: hidden;

                img{
                    position: absolute;
                    width: 100svw;
                    top: 0%;
                    left: 0;
                    transform: translateX(-10%);
                }

				transition: all 0.5s ease;

				&:global(.jpeged) {
					width: 100%;

                    img{
                        transform: translateX(0);
                    }
				}
			}
			.container {
				height: 100%;
			}
		}

		&-info {
			display: flex;
			opacity: 0;
			flex-direction: column;
			gap: 20px;
			width: 65%;
			position: absolute;
			top: 0;
			left: 0;
            pointer-events: none;

			transition:
				opacity 0.3s ease,
				transform 0.8s ease;

			&:first-child {
				position: relative;
			}
			&:global(.visible) {
				opacity: 1;
                pointer-events: all;
			}
			&.active {
				transform: translateX(0) !important;
			}
			&:global(.next) {
				transform: translateX(3%);
			}
			&:global(.prev) {
				transform: translateX(-3%);
			}

			p {
				color: #fff;
			}
			h2 {
				color: #fff;
				text-wrap: balance;
			}

			a {
				margin-top: 20px;
			}
		}
	}

	.handles {
		display: flex;
		align-items: center;
		gap: 20px;

		&-pagination {
			display: flex;

			align-items: center;
			gap: 5px;

			div {
				border: 0.4px solid #d2d2d2;
				border-radius: 100%;
				width: 10px;
				height: 10px;

				&.active {
					background-color: #d2d2d2;
				}
			}
		}

		&-controls {
			display: flex;

			align-items: center;
			gap: 30px;

			button:last-child {
				svg {
					transform: rotate(180deg);
				}
			}

            button{
                &:disabled{
                    svg{
                        opacity: 0.6;
                    }
                }
            }
		}
	}
</style>
