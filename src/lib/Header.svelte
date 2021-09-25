<script>
import Navbar from './Navbar.svelte';
import translations from '../data/translations';
import {
    dict,
    locale,
    t
} from '../data/i18n';
$: languages = Object.keys(translations);
$: dict.set(translations);
</script>

<Navbar />

<div class="w-full flex flex-col lg:flex-row items-center justify-center text-white" id="hero">
    <div class="flex flex-col items-center lg:flex-row">
        <div class="flex flex-col items-baseline my-2 md:my-8 mx-16 md:mx-16">
            <h1 class="max-w-md text-5xl md:text-6xl font-semibold py-4">{$t('hero_slogan')[0].text} {$t('hero_slogan')[1].text} {$t('hero_slogan')[2].text} {$t('hero_slogan')[3].text}</h1>
            <br>
            <!-- <p class="font-thin">{$t('hero_slogan')[3].text}</p> -->
            <br>
            <a class="flex flex-row items-center justify-center px-8 py-4 rounded-full font-semibold transition duration-500 ease-in-out transform hover:-translate-1 hover:scale-110" id="btn" href="#contact">{$t('hero_slogan')[5].text}</a>
            <br>
        </div>
        <div class=" w-4/5 lg:w-auto">
            <img src="/hero-img.png" class="" alt="">
        </div>
    </div>
</div>

<style>
#hero {
    background-color: #0D0D2B;
}

#btn {
    background: linear-gradient(90deg, rgba(61, 77, 161, 1) 48%, rgba(81, 102, 213, 1) 100%);
}

p {
    color: #E0E0E0;
    opacity: 0.8;
}

img {
    mix-blend-mode: color-dodge;
}
</style>
