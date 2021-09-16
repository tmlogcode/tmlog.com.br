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

<div data-aos="slide-right" data-aos-delay="1200" class="flex flex-col justify-around items-center lg:flex-row about">
    {#each $t('values_list') as item}
    <div class="my-7 max-w-sm text-white">
        <h1 class="py-3 text-2xl font-bold">{item.title}</h1>
        <p class="font-normal opacity-70">{item.p}</p>
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
