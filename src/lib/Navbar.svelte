<script>
let clicked = false;

function menu() {
    if (clicked == false) {
        menuOpen();
    } else {
        menuClose();
    }
}

function menuOpen() {
    console.log('OPEN');
    clicked = true;
    let menu = document.querySelector('#menuMobile');
    menu.style.display = 'flex';
}

function menuClose() {
    console.log('CLOSE');
    clicked = false;
    let menu = document.querySelector('#menuMobile');
    menu.style.display = 'none';
}

import translations from '../data/translations';
import {
    dict,
    locale,
    t
} from '../data/i18n';
$: languages = Object.keys(translations);
$: dict.set(translations);
</script>

<nav class="w-full h-40 flex justify-around items-center">
    <a href="/" class="transition duration-500 ease-in-out transform hover:-translate-1 hover:scale-110"><img src="/logo-full-white.svg" alt="" class=""></a>
    <ul class="hidden sm:flex justify-around items-center">
        {#each $t('navbar') as item}
        <li class="mx-8  font-normal">
            <a href="{item.path}">{item.label}</a>
        </li>
        {/each}
        <li class="mr-2 md:mr-4 lg:mr-11" id="divisor">|</li>
        <a href="#contact" class=""><li class="mx-8 px-10 py-4 rounded-full border-white border hover:animate-pulse" id="contact-btn">{$t('contact')}</li></a>
        <select bind:value={$locale} class="uppercase text-white" id="btn-lang">
            {#each languages as lang}
            <option value={lang} class="uppercase flex items-center justify-center">
                {lang}
            </option>
            {/each}
        </select>
    </ul>
    <button class="sm:hidden" on:click={menu}>
        {#if clicked == false}
        <img src="/menu.svg" alt="">
        {:else}
        <img src="/menu-close.svg" alt="">
        {/if}
    </button>
</nav>
<ul class="hidden flex flex-col items-center bg-black" id="menuMobile">
    {#each $t('navbar') as item}
    <li class="my-8 font-thin">
        <a href="{item.path}">{item.label}</a>
    </li>
    {/each}
    <select bind:value={$locale} class="uppercase text-white mt-4 mb-4" id="btn-lang">
        {#each languages as lang}
        <option value={lang} class="uppercase flex items-center justify-center">
            {lang}
        </option>
        {/each}
    </select>
</ul>

<style>
img {
    height: 90px;

}

#btn-lang {
    background-color: #0D0D2B;
}

li {
    color: #fff;
}

nav {
    background-color: #0D0D2B;
}

#divisor {
    color: #F2F2F2 !important;
    opacity: 0.3;
}

button {
    width: 50px;
}

#menuMobile {
    background-color: #0D0D2B;
    animation-name: open;
    animation-duration: 0.2s;
    animation-iteration-count: 1;
    animation-fill-mode: forwards;
}

@keyframes open {
    0% {
        background-color: #0D0D2B;
        height: 0px;
    }

    100% {
        background-color: #0D0D2B;
        height: 300px;
    }
}
</style>
