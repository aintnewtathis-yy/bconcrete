<script>
	import Hero from "$lib/components/Hero.svelte";
	import Categories from "$lib/components/Categories.svelte";
	import Banner from "$lib/components/Banner.svelte";
	import MiniCatalog from "../lib/components/Mini-catalog.svelte";
	import WideVariety from "../lib/components/WideVariety.svelte";
	import NewsRow from "../lib/components/NewsRow.svelte";

    const products = [
		{
			url: '#url',
			image: '/kashpo.jpg',
			colors: ['#cbc2b8', '#c5b7a3', '#a98f77', '#5d151a', '#333333'],
			title: 'Кашпо Wegner CH07 Shell',
			desc: 'classic collection',
			price: 15000
		},
		{
			url: '#url',
			image: '/kashpo2.jpg',
			colors: ['#cbc2b8', '#c5b7a3', '#a98f77', '#5d151a', '#333333'],
			title: 'Кашпо Wegner CH07 Shell',
			desc: 'classic collection',
			price: 15000
		},
		{
			url: '#url',
			image: '/kashpo3.jpg',
			colors: ['#cbc2b8', '#c5b7a3', '#a98f77', '#5d151a', '#333333'],
			title: 'Кашпо Wegner CH07 Shell',
			desc: 'classic collection',
			price: 15000
		}
	];
    const products2 = [
		{
			url: '#url',
			image: '/kashpo.jpg',
			colors: ['#cbc2b8', '#c5b7a3', '#a98f77', '#5d151a', '#333333'],
			title: 'Кашпо Wegner CH07 Shell',
			desc: 'classic collection',
			price: 15000
		},
		{
			url: '#url',
			image: '/kashpo2.jpg',
			colors: ['#cbc2b8', '#c5b7a3', '#a98f77', '#5d151a', '#333333'],
			title: 'Кашпо Wegner CH07 Shell',
			desc: 'classic collection',
			price: 15000
		},
		{
			url: '#url',
			image: '/kashpo3.jpg',
			colors: ['#cbc2b8', '#c5b7a3', '#a98f77', '#5d151a', '#333333'],
			title: 'Кашпо Wegner CH07 Shell',
			desc: 'classic collection',
			price: 15000
		},
		{
			url: '#url',
			image: '/kashpo4.jpg',
			colors: ['#cbc2b8', '#c5b7a3', '#a98f77', '#5d151a', '#333333'],
			title: 'Кашпо Wegner CH07 Shell',
			desc: 'classic collection',
			price: 15000
		},
		{
			url: '#url',
			image: '/kashpo5.jpg',
			colors: ['#cbc2b8', '#c5b7a3', '#a98f77', '#5d151a', '#333333'],
			title: 'Кашпо Wegner CH07 Shell',
			desc: 'classic collection',
			price: 15000
		},
		{
			url: '#url',
			image: '/kashpo6.jpg',
			colors: ['#cbc2b8', '#c5b7a3', '#a98f77', '#5d151a', '#333333'],
			title: 'Кашпо Wegner CH07 Shell',
			desc: 'classic collection',
			price: 15000
		}
	];
</script>

<Hero />
<Categories />
<Banner title="Проведите эту зиму в уюте и комфорте c коллецией BazhenovConcrete" subtitle="Столешница Wegner CH07 Shell" url="#url" bgImage="/banner.png" />
<MiniCatalog largeProduct=true products={products} minititle="Новинки" />
<MiniCatalog largeProduct=false products={products2} minititle="Актуальное" />
<Banner title="Проведите эту зиму в уюте и комфорте c коллецией BazhenovConcrete" subtitle="Столешница Wegner CH07 Shell" url="#url" bgImage="/banner1.png" />
<WideVariety />
<NewsRow />