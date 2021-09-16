<script>
import translations from '../data/translations';
import {
    dict,
    locale,
    t
} from '../data/i18n';
$: languages = Object.keys(translations);
$: dict.set(translations);

import {
    getContext
} from 'svelte';
import Surprise from './Surprise.svelte';

const {
    open
} = getContext('simple-modal');

const showSurprise = () => {
    open(Surprise, {
        message: "Cotação enviada!"
    });
    setTimeout(function() {
        document.getElementById("fs-frm").reset();
    }, 2000);
};
</script>

<div id="contact" class="w-auto flex flex-col xl:flex-row items-center justify-center py-8">
    <h2 class="text-5xl md:text-4xl xl:mr-32 font-semibold text-center max-w-xl py-14 text-white ">{$t('contact_data')[0].heading} 📝</h2>
    <form class="flex flex-col p-8 mx-8 rounded-3xl card" id="fs-frm" target="formSubmitFrame" name="survey-form" accept-charset="utf-8" action="https://formspree.io/f/xeqvkrav" method="post" on:submit={showSurprise}>
        <fieldset id="fs-frm-inputs" class="flex flex-col">
            <label class="text-white my-2" for="full-name" id="margin">{$t('contact_data')[0].email_list[0].list1}</label>
            <input class=" my-2" type="text" name="Nome" id="full-name" placeholder={$t('contact_data')[0].placeholder_list[0].list1} required>
            <label class="text-white my-2" for="email-address">{$t('contact_data')[0].email_list[0].list2}</label>
            <input class="my-2" type="email" name="_replyto" id="email-address" placeholder={$t('contact_data')[0].placeholder_list[0].list2} required>
            <label class="text-white my-2" for="phone">{$t('contact_data')[0].email_list[0].list3}</label>
            <input class="my-2" type="text" name="Telefone" id="phone" placeholder={$t('contact_data')[0].placeholder_list[0].list3} required>
            <fieldset class="my-2 flex flex-row items-center justify-between" id="fs-frm-selects">
                <label class="text-white my-2" for="timely">1. {$t('contact_data')[0].email_list[0].list4}</label>
                <select class="my-2 p-1 rounded-md" name="Tipo de serviço" id="timely" required>
                    <option value="Choose" selected={$t('contact_data')[0].services_list[0].list1} disabled="">{$t('contact_data')[0].services_list[0].list1}</option>
                    <option value={$t('contact_data')[0].services_list[0].list1}>{$t('contact_data')[0].services_list[0].list2}</option>
                    <option value={$t('contact_data')[0].services_list[0].list2}>{$t('contact_data')[0].services_list[0].list3}</option>
                    <option value={$t('contact_data')[0].services_list[0].list3}>{$t('contact_data')[0].services_list[0].list4}</option>
                    <option value={$t('contact_data')[0].services_list[0].list4}>{$t('contact_data')[0].services_list[0].list5}</option>
                    <option value={$t('contact_data')[0].services_list[0].list5}>{$t('contact_data')[0].services_list[0].list6}</option>
                    <option value={$t('contact_data')[0].services_list[0].list6}>{$t('contact_data')[0].services_list[0].list7}</option>
                </select>
            </fieldset>
            <label class="text-white my-2" for="cargo-origin">2. {$t('contact_data')[0].email_list[0].list5}</label>
            <input class="my-2" type="text" name="Origem da carga" id="cargo-origin" placeholder={$t('contact_data')[0].placeholder_list[0].list4} required>
            <label class="text-white my-2" for="cargo-destination">3. {$t('contact_data')[0].email_list[0].list6}</label>
            <input class="my-2" type="text" name="Destino da carga" id="cargo-destination" placeholder={$t('contact_data')[0].placeholder_list[0].list5} required>
            <label class="text-white my-2" for="cargo-description">{$t('contact_data')[0].email_list[0].list7}</label>
            <textarea class="my-2" rows="3" name="Descrição da carga" id="message"
                placeholder=""
                required=""></textarea>
            <fieldset class="my-2" id="fs-frm-selects">
                <label class="text-white my-2" for="importer">{$t('contact_data')[0].email_list[0].list8}</label>
                <select class="my-2 p-1 rounded-md" name="Já realizou transporte internacional?" id="importer" required>
                    <option value={$t('contact_data')[0].services_list[0].list1} selected={$t('contact_data')[0].services_list[0].list1} disabled="">{$t('contact_data')[0].services_list[0].list1}</option>
                    <option value={$t('contact_data')[0].importer_list[0].list1}>{$t('contact_data')[0].importer_list[0].list2}</option>
                    <option value={$t('contact_data')[0].importer_list[0].list2}>{$t('contact_data')[0].importer_list[0].list3}</option>
                </select>
            </fieldset>
            <input type="hidden" name="_subject" id="email-subject" value="Nova cotação solicitada:">
        </fieldset>
        <input id="submit" class=" py-4 rounded-3xl mt-6" type="submit" value={$t('contact_data')[0].email_list[0].list9}>
        <iframe name="formSubmitFrame" tile="Holds Submitted form data" rel="nofollow" class="d-none"></iframe>
    </form>
</div>

<style>

.card {
    background: rgb(85, 86, 94);
    background: linear-gradient(180deg, rgba(85, 86, 94, 0.20211834733893552) 0%, rgba(85, 86, 94, 0.04525560224089631) 100%);
}

.card2 {
    background: rgb(61, 77, 161);
    background: linear-gradient(141deg, rgba(61, 77, 161, 0.17690826330532217) 0%, rgba(85, 86, 94, 0.20211834733893552) 100%);
}

iframe {
    height: 0px;
    width: 0px;
}

input[type="text"],
input[type="email"] {
  background-color: #0D0D2B;
  padding: 10px;
  color: #fff;
}

textarea {
  background-color: #0D0D2B;
  color: #fff;
  resize: none;
}

select {
    background-color: #3D4DA1;
    color: #fff;
}

input[type="submit"] {
    background: linear-gradient(90deg, rgba(61, 77, 161, 1) 48%, rgba(81, 102, 213, 1) 100%);
    transition: transform .2s;
    color: #fff;
}
input[type="submit"]:hover {
    transform: scale(1.05);
}

</style>
