<script>

export let stats = [];

import translations from '../data/translations';
    import { dict, locale, t } from '../data/i18n';
    $: languages = Object.keys(translations);
    $: dict.set(translations);

</script>
<div id="container" class="w-full h-auto flex items-center justify-center">
    <div class="flex flex-col lg:flex-row my-8">
        {#each $t('stats') as item}
            <div class="flex items-center p-4 m-1 text-white">
                <img src={item.img} alt="">
                <div class="mx-4">
                    <h1 class="font-semibold text-3xl">{item.title}</h1>
                    <p class="font-thin">{item.p}</p>
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
</style>