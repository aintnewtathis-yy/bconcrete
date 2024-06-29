<script>
	export let bgImage
	export let subtitle
	export let title
	export let url
</script>

<section class="banner-section --margin-bottom" >
	<div class="container">
		<div class="banner" style="background-image: url('{bgImage}');">
			<p>{subtitle}</p>
			<h2 class="--text-xl">{title}</h2>
			<a href={url} class="btn-main">Перейти в каталог</a>
		</div>
	</div>
</section>

<style lang="scss">
	.banner {
		display: flex;
		flex-direction: column;
		align-items: center;
		background-position: center center;
		background-size: cover;
		background-repeat: no-repeat;
		padding-top: 170px;
		padding-bottom: 90px;
		border-radius: 10px;
		gap: 20px;

		a {
			margin-top: 190px;
		}

		h2 {
			width: 90%;
			text-wrap: balance;
			color: #fff;
			margin: 0 auto;
			text-align: center;
		}
		p {
			color: #fff;
		}
	}
</style>
