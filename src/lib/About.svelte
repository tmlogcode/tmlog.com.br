<script>

    export let about = [];
    import translations from '../data/translations';
    import { dict, locale, t } from '../data/i18n';
    $: languages = Object.keys(translations);
    $: dict.set(translations);

</script>

<div id="about" class="w-full h-auto text-white text-center flex flex-col items-center">
    <h1 class="text-4xl font-semibold py-2">{$t('about')[0].heading}</h1>
    <p class="font-thin my-8 max-w-md">{$t('about')[0].title}</p>
    <div class="flex flex-col items-center bg-white rounded-xl font-darkblue text-center max-w-md lg:max-w-xl px-8 shadow-lg">
        <p class="py-8 md:max-w-xl">{$t('about')[0].why_list[0].text1}</p>
        <p class="py-8 md:max-w-xl">{$t('about')[0].why_list[0].text2}</p>
    </div>
    <h1 class="text-4xl font-semibold py-8">{$t('values')[0].heading}</h1>
    <div class="flex flex-col justify-around lg:flex-row">
        {#each $t('values_list') as item}
        <div class="card m-8 p-4 max-w-sm rounded-xl">
            <h1 class="py-3 text-2xl font-semibold">{item.title}</h1>
            <p class="font-thin">{item.p}</p>
        </div>
        {/each}
    </div>
</div>

<style>
    #about {
        background: rgb(13,13,43);
        background: linear-gradient(180deg, rgba(13,13,43,1) 0%, rgba(61,77,161,1) 100%);
    }

    .font-darkblue {
        color: #0D0D2B;
    }

    .card {
        background-color: #3D4DA1;
        opacity: 0.9;
    }
</style>