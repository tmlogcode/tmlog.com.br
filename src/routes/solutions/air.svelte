<script>
	import Footer from './../../lib/Footer.svelte';
	import Navbar from './../../lib/Navbar.svelte';

    import translations from './../../data/translations';
    import { dict, locale, t } from './../../data/i18n';
    $: languages = Object.keys(translations);
    $: dict.set(translations);
</script>

<Navbar />

<div id="airbanner" class="w-full flex items-center justify-center md:justify-end  md:px-36">
	<div class="flex flex-col items-center justify-center">
        <img src="/logo-mini-white.svg" alt="" class="logo-mini">
		<h1 class="text-white font-semibold text-6xl">{$t('air')[0].title}</h1>
		<div class="arrow my-8">
			<span></span>
			<span></span>
			<span></span>
		</div>
	</div>
</div>

<div id="custom" class="w-full flex flex-col md:flex-row items-center justify-center">
    <div>
        <h1 class="text-white text-3xl font-thin max-w-lg text-center pt-12 md:pt-36 px-4">{$t('air')[0].desc_1}</h1>
        <h2 class="text-white text-3xl font-semibold max-w-lg text-center lb-12 md:pb-36 px-4">{$t('air')[0].desc_2}</h2>
    </div>
    <div class="py-24">
        <ul class="text-white">
            <li class="flex flex-row items-center my-8"><img id="icon" class="mx-4" src="../check.svg" alt="">{$t('air')[0].list_1}</li>
            <li class="flex flex-row items-center my-8"><img id="icon" class="mx-4" src="../check.svg" alt="">{$t('air')[0].list_2}</li>
            <li class="flex flex-row items-center my-8"><img id="icon" class="mx-4" src="../check.svg" alt="">{$t('air')[0].list_3}</li>
            <li class="flex flex-row items-center my-8"><img id="icon" class="mx-4" src="../check.svg" alt="">{$t('air')[0].list_4}</li>
            <li class="flex flex-row items-center my-8"><img id="icon" class="mx-4" src="../check.svg" alt="">{$t('air')[0].list_5}</li>
            <li class="flex flex-row items-center my-8"><img id="icon" class="mx-4" src="../check.svg" alt="">{$t('air')[0].list_6}</li>
            <li class="flex flex-row items-center my-8"><img id="icon" class="mx-4" src="../check.svg" alt="">{$t('air')[0].list_7}</li>
        </ul>
    </div>
</div>
<div class="w-full" id="background-color">
    <div class="arrow pb-12">
        <span></span>
        <span></span>
        <span></span>
    </div>
</div>

<div id="custom" class="w-full flex flex-col md:flex-row items-center justify-center pb-12">
    <img src="/air.png" alt="" class="my-8">
    <div class="flex flex-col items-center justify-center">
        <h2 class="text-white text-3xl font-thin max-w-lg text-center px-4 py-8">{$t('air')[0].footer_1}</h2>
        <h2 class="text-white text-3xl font-semibold max-w-lg text-center px-4 py-8">{$t('air')[0].footer_2}</h2>
    </div>
</div>
<div class="flex flex-col lg:flex-row">
    <div class="flex flex-col items-center justify-center">
    </div>
</div>
<div class="w-full flex flex-col md:flex-row items-center justify-center background-color">
    <img src="/logo-mini-white.svg" alt="" class="logo-mini">
    <h2 class="text-white text-3xl font-semibold max-w-sm text-center px-4 pb-4 pt-4">{$t('air')[0].more_1} <a class="btn" href="#">{$t('air')[0].more_2}</a></h2>
</div>
<Footer />
<style>

	#airbanner {
		height: 800px;
		background-color: #0D0D2B;
		background-image: url("/air-banner.jpeg");
		background-position: right;
		background-size: cover;
		background-blend-mode: luminosity;
	}

    #background-color {
        background-color: #0D0D2B;
    }

    .background-color {
        background: rgb(61,77,161);
    background: linear-gradient(280deg, rgba(61,77,161,1) 0%, rgba(13,13,43,1) 100%);
    }

    h1 {
		color: white;
	}

    .logo-mini {
        height: auto;
        width: 100px;
        margin-top: 30px;
        margin-bottom: 30px;
    }

	.arrow {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .arrow span {
        display: block;
        width: 30px;
        height: 30px;
        border-bottom: 5px solid #06A8FF;
        border-right: 5px solid #06A8FF;
        transform: rotate(45deg);
        margin: -10px;
        animation: animate 2s infinite;
    }

    .arrow span:nth-child(2) {
        animation-delay: -0.2s;
    }

    .arrow span:nth-child(3) {
        animation-delay: -0.4s;
    }

    @keyframes animate {
        0% {
            opacity: 0;
            transform: rotate(45deg) translate(-20px, -20px);
        }

        50% {
            opacity: 1;
        }

        100% {
            opacity: 0;
            transform: rotate(45deg) translate(20px, 20px);
        }
    }

    img {
        mix-blend-mode: lighten;
    }

    #icon {
        width: 30px;
    }

    #custom {
        background-color: #0D0D2B;
    }

</style>