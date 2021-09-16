<script>
export let about = [];
import translations from '../data/translations';
import {
    dict,
    locale,
    t
} from '../data/i18n';
$: languages = Object.keys(translations);
$: dict.set(translations);
</script>

<div id="about" class="w-full h-auto text-white flex-col items-center justify-center about pt-20">
    <div class="flex flex-col xl:flex-row items-center justify-center">
        <div class="flex flex-col items-center justify-center p-12 mx-6 mb-8 md:mx-32 lg:mx-12 bg-transparent rounded-3xl card">
            <p data-aos="fade-right" data-aos-delay="50" class="font-thin max-w-lg text-2xl text-center"><b>{$t('about')[0].title}</b></p>
            <lottie-player data-aos="fade-left" data-aos-delay="400" class="" src="https://assets2.lottiefiles.com/packages/lf20_1epnq1b8.json"  background="transparent"  speed="1"  style="width: auto; height: auto;"  loop autoplay></lottie-player>
        </div>
        <div data-aos="fade-right" data-aos-delay="750" class="flex flex-col items-center justify-center md:rounded-xl mx-7 md:mx-32 lg:mx-8 p-12 bg-transparent rounded-3xl card2">
            <p class="text-lg md:max-w-3xl mb-4">{$t('about')[0].why_list[0].text1}</p>
            <p class="text-lg md:max-w-3xl">{$t('about')[0].why_list[0].text2}</p>
        </div>
    </div>
</div>

<style>
.about {
    background: rgb(13, 13, 43) !important;
}

.card {
    background: rgb(85, 86, 94);
    background: linear-gradient(180deg, rgba(85, 86, 94, 0.20211834733893552) 0%, rgba(85, 86, 94, 0.04525560224089631) 100%);
}

.card2 {
    background: rgb(61, 77, 161);
    background: linear-gradient(141deg, rgba(61, 77, 161, 0.17690826330532217) 0%, rgba(85, 86, 94, 0.20211834733893552) 100%);
}
</style>
