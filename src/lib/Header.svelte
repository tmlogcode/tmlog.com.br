<script>
	import Navbar from './Navbar.svelte';
	import translations from '../data/translations';
    import { dict, locale, t } from '../data/i18n';
    $: languages = Object.keys(translations);
    $: dict.set(translations);
</script>

<Navbar />

<div class="w-full flex flex-col lg:flex-row items-center justify-center text-white" id="hero">
	<div class="wraper flex flex-col items-center lg:flex-row">  
	<div class="flex flex-col my-8">
		<h1 class="text-4xl md:text-6xl font-semibold">{$t('hero_slogan')[0].text}</h1>
		<h1 class="text-4xl md:text-6xl font-semibold">{$t('hero_slogan')[1].text}</h1>
		<h1 class="text-4xl md:text-6xl font-semibold">{$t('hero_slogan')[2].text}</h1>
		<br>
		<!-- <p class="font-thin">{$t('hero_slogan')[3].text}</p> -->
		<br>
		<a class="flex items-center justify-around w-52 h-14 rounded-full px-2" id="btn" href="#contact">{$t('hero_slogan')[4].text}<img src="/arrow-right.svg" alt=""></a>
		<br>
	</div>
	<div>
		<img src="/hero.png" alt="">
	</div>
</div>
</div>

<style>
	#hero {
		background-color: #0D0D2B;
	}

	#btn {
		background-color: #3D4DA1;
	}

	p {
		color: #E0E0E0;
		opacity: 0.8;
	}

	img {
		mix-blend-mode: color-dodge;
	}

	.wraper {
		max-width: 80%;	
	}
</style>
