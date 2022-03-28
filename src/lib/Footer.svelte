<script>
    import translations from '../data/translations';
    import {
        dict,
        locale,
        t
    } from '../data/i18n';
    $: languages = Object.keys(translations);
    $: dict.set(translations);
</script>

<div id="footer" class="w-full flex flex-col md:flex-row justify-center text-white">
    <div class="w-50 flex flex-col justify-center items-center mx-12">
        <img class="my-8 max-w-sm" style="max-width: 280px;" src="/logo-full-white.svg" alt="">
        <a href="mailto:contato@tmlog.com.br" class="font-normal my-1">contato@tmlog.com.br</a>
        <a href="tel:+551149785939" class="mb-6">+55 11 4978-5939</a>
        <div class="flex">
            <a href="https://www.linkedin.com/company/tmlog/">
                <img class="px-1" style="width: 35px; height: 35px;" src="/linkedin.svg" alt="">
            </a>
            <a href="https://www.instagram.com/tmloglogistics/">
                <img class="px-1 ml-4" style="width: 35px; height: 35px;" src="/instagram.svg" alt="">
            </a>
            <a href="https://twitter.com/tmlog_logistics">
                <img class="px-1 ml-4" style="width: 35px; height: 35px;" src="/twitter.svg" alt="">
            </a>
        </div>
    </div>
    <div class="w-50 flex flex-col items-center mx-12">
        <div class="flex">
            <div class="flex flex-col py-4 mx-8">
                <h1 class="text-xl font-bold py-4">{$t('footer_data')[0].fast_links[0].title}</h1>
                <a class="font-normal pb-3 opacity-70" href="/">{$t('footer_data')[0].fast_links[0].home}</a>
                <a class="font-normal pb-3 opacity-70" href="#services">{$t('footer_data')[0].fast_links[0].services}</a>
                <a class="font-normal pb-3 opacity-70" href="#about">{$t('footer_data')[0].fast_links[0].about}</a>
                <a class="font-normal opacity-70" href="#contact">{$t('footer_data')[0].fast_links[0].contact}</a>
            </div>
            <div class="flex flex-col py-4 mx-8">
                <h1 class="text-xl font-semibold py-4">{$t('footer_data')[0].pages[0].title}</h1>
                <a class="font-normal pb-3 opacity-70" href="/services/air-freight">{$t('footer_data')[0].pages[0].air}</a>
                <a class="font-normal pb-3 opacity-70" href="/services/sea-freight">{$t('footer_data')[0].pages[0].sea}</a>
                <a class="font-normal pb-3 opacity-70" href="/services/truck-freight">{$t('footer_data')[0].pages[0].truck}</a>
                <a class="font-normal pb-3 opacity-70" href="/services/integrated-logistics">{$t('footer_data')[0].pages[0].integrated}</a>
                <a class="font-normal opacity-70" href="/services/cargo-insurance">{$t('footer_data')[0].pages[0].cargo}</a>
            </div>
        </div>
    </div>
</div>
<div id="footer-2" class="flex w-full items-center justify-around">
    <div class="pt-6">
        <h1 class="text-sm text-white pt-2 pb-2 text-acave text-center">Rua Giovanni Battista Pirelli, 271, Sala 207, Vila Homero Thon, Santo André, SP - Brasil - CEP 09111-340</h1>
    </div>
</div>
<h2 id="copyright" class="text-xs text-white pt-2 pb-2 text-acave text-center">Copyright© 2020. Todos os direitos reservados a TMLOG - International Logístics.</h2>

<style>
#footer,#footer-2 {
    background: linear-gradient(90deg, rgba(61, 77, 161, 1) 48%, rgba(81, 102, 213, 1) 100%);
}
#copyright {
    background-color: #0D0D2B;
}
</style>