<script>

    import translations from '../data/translations';
    import {
        dict,
        locale,
        t
    } from '../data/i18n';
    $: languages = Object.keys(translations);
    $: dict.set(translations);

    // import Swiper core and required modules
    import { Navigation, Pagination, Scrollbar, A11y, Autoplay } from 'swiper';
  
    import { Swiper, SwiperSlide } from 'swiper/svelte';
  
    // Import Swiper styles
    import 'swiper/css';
    import 'swiper/css/navigation';
    import 'swiper/css/pagination';
    import 'swiper/css/scrollbar';
</script>

<div class=" flex flex-col justify-center items-center md:flex-row">
    <div class="w-full md:w-1/2">
        <Swiper
        class=""
        modules={[Navigation, Pagination, Scrollbar, A11y, Autoplay]}
        spaceBetween={50}
        slidesPerView={1}
        autoplay={{
            delay: 5000,
            disableOnInteraction: false,
            }}
        loop
        navigation
        pagination={{ clickable: true }}
        on:slideChange={() => console.log('slide change')}
        on:swiper={(e) => console.log(e.detail[0])}
      >
        <SwiperSlide class="text-white">
            <h1 class="py-6 px-16 font-bold text-2xl">{$t('rotative')[0].title0}</h1>
            <p class="pb-12 px-16">{$t('rotative')[0].text0}</p>
        </SwiperSlide>
        <SwiperSlide class="text-white">
            <h1 class="py-6 px-16 font-bold text-2xl">{$t('rotative')[0].title1}</h1>
            <p class="pb-12 px-16">{$t('rotative')[0].text1}</p>
        </SwiperSlide>
        <SwiperSlide class="text-white">
            <h1 class="py-6 px-16 font-bold text-2xl">{$t('rotative')[0].title2}</h1>
            <p class="pb-12 px-16">{$t('rotative')[0].text2}</p>
        </SwiperSlide>
        ...
      </Swiper>
    </div>
    <img class="w-full" src="carossel.svg" alt="">
</div>

<style>
    /* img {
        width: 500px;
        height: 500px;
    } */
</style>