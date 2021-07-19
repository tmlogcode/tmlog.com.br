
<script>
    
    export let solutions = [];
    import translations from '../data/translations';
    import { dict, locale, t } from '../data/i18n';
    $: languages = Object.keys(translations);
    $: dict.set(translations);
    
</script>

<div id="solutions" class="w-full flex flex-col items-center bg-yellow-400 text-white">
    <div class="arrow">
        <span></span>
        <span></span>
        <span></span>
    </div>
    {#each $t('solutions_data') as item}
    <div class="flex flex-col lg:flex-row items-center justify-center py-6 max-w-7xl">
        <img src={item.img} alt="">
        <div class="flex flex-col px-4 py-12">
            <h1 class="py-4 text-4xl font-semibold">{item.title}</h1>
            <p class="py-4 opacity-60 max-w-screen-sm font-thin">{item.p}</p>
            <a class="flex items-center" href={item.link}>
                <div class="btn py-3 px-8 rounded-full">{item.more}</div>
            </a>
        </div>
    </div>
    {/each}
</div>

<style>
    #solutions {
        background-color: #0D0D2B;
        /* background-image: url("./background.gif");
        background-position: center;
        background-size: cover;
        background-blend-mode: color-dodge; */
    }

    img {
        mix-blend-mode: lighten;
    }

    .btn {
        background-color: #3D4DA1;
    }

    .btn:hover {
        background-color: #324084;
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

</style>