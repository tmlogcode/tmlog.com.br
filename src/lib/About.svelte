<script>

    export let about = [];
    import translations from '../data/translations';
    import { dict, locale, t } from '../data/i18n';
    $: languages = Object.keys(translations);
    $: dict.set(translations);

</script>

<div id="about" class="w-full h-auto text-white flex-col items-center justify-center">
    <div class="flex flex-col md:flex-row items-center justify-center">
        <div class="flex flex-col items-center justify-center px-5">
            <h1 class="text-4xl font-semibold py-2 ">{$t('about')[0].heading}</h1>
            <p class="font-thin mt-5 mb-5 max-w-lg text-lg text-center"><b>{$t('about')[0].title}</b></p>
        </div>
        <div id="bg" class="flex flex-col items-center justify-center font-darkblue px-5 md:rounded-xl">
            <p class="pt-10 pb-5 text-lg md:max-w-xl">{$t('about')[0].why_list[0].text1}</p>
            <p class="pb-10 text-lg md:max-w-xl">{$t('about')[0].why_list[0].text2}</p>
        </div>
    </div>
    <div class="flex flex-col justify-around items-center lg:flex-row">
        {#each $t('values_list') as item}
        <div class="card my-7 max-w-sm rounded-xl">
            <h1 class="py-3 text-2xl font-semibold">{item.title}</h1>
            <p class="font-thin">{item.p}</p>
            <br>
            <ul class=" text-left px-5">
                <li class="my-2">{item.p1}</li>
                <li class="my-2">{item.p2}</li>
                <li class="my-2">{item.p3}</li>
                <li class="my-2">{item.p4}</li>
            </ul>
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

    #bg {
        background-image: url(/white-vector.jpg);
        background-position: center;
        background-size: cover;
    }

</style>