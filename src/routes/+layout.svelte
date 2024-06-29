<script>
	import '../app.scss';
	import Lenis from 'lenis';
	import { onMount } from 'svelte';

	onMount(() => {
        const lenis = new Lenis();

		function raf(time) {
			lenis.raf(time);
			requestAnimationFrame(raf);
		}

		requestAnimationFrame(raf);
    })
    
</script>

<main>
	<slot />
</main>
