<script>

export let stats = [];

import translations from '../data/translations';
    import { dict, locale, t } from '../data/i18n';
    $: languages = Object.keys(translations);
    $: dict.set(translations);

</script>
<div id="container" class="w-full h-auto flex items-center justify-center">
    <div data-aos="fade-up" data-aos-delay="0" class="flex flex-col lg:flex-row my-8">
        {#each $t('stats') as item}
            <div class="flex items-center p-4 mx-10 my-8 md:my-1 text-white bg-transparent rounded-3xl" id="card">
                <img src={item.img} alt="">
                <div class="mx-4">
                    <h1 class="font-semibold text-3xl">{item.title}</h1>
                    <p class="font-normal opacity-70">{item.p}</p>
                </div>
            </div>
        {/each}
    </div>
</div>

<style>

    #container {
        background-color: #0D0D2B;
    }
/* 
    img {
        width: 80px;
    }
     */

     #card {
        background: rgb(85,86,94);
background: linear-gradient(180deg, rgba(85,86,94,0.20211834733893552) 0%, rgba(85,86,94,0.04525560224089631) 100%);
transition: transform .2s;
     }

     #card:hover {
        transform: scale(1.2);
     }
</style>