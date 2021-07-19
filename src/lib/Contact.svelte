<script>

import translations from '../data/translations';
import { dict, locale, t } from '../data/i18n';
$: languages = Object.keys(translations);
$: dict.set(translations);

import { getContext } from 'svelte';
import Surprise from './Surprise.svelte';
  
const { open } = getContext('simple-modal');
  
const showSurprise = () => {
    open(Surprise, { message: "Cotação enviada!" });
    setTimeout(function(){ document.getElementById("fs-frm").reset(); }, 2000);
};

</script>

<div id="contact" class="w-full flex flex-col items-center">
    <div class="login-box w-full max-w-2xl p-12 m-8 md:rounded-xl">
        <h2 class="text-3xl font-semibold text-center max-w-xl py-14 text-white">{$t('contact_data')[0].heading}</h2>
        <form id="fs-frm" target="formSubmitFrame" name="survey-form" accept-charset="utf-8" action="https://formspree.io/f/xeqvkrav" method="post" on:submit={showSurprise}>
          <fieldset id="fs-frm-inputs">
            <label class="text-white" for="full-name" id="margin">{$t('contact_data')[0].email_list[0].list1}</label>
            <input type="text" name="Nome" id="full-name" placeholder={$t('contact_data')[0].placeholder_list[0].list1} required>
            <label class="text-white" for="email-address">{$t('contact_data')[0].email_list[0].list2}</label>
            <input type="email" name="_replyto" id="email-address" placeholder={$t('contact_data')[0].placeholder_list[0].list2} required>
            <label class="text-white" for="phone">{$t('contact_data')[0].email_list[0].list3}</label>
            <input type="text" name="Telefone" id="phone" placeholder={$t('contact_data')[0].placeholder_list[0].list3} required>
            <fieldset id="fs-frm-selects">
                <label class="text-white" for="timely">1. {$t('contact_data')[0].email_list[0].list4}</label>
                <select name="Tipo de serviço" id="timely" required>
                    <option value="Choose" selected="" disabled="">{$t('contact_data')[0].services_list[0].list1}</option>
                    <option value={$t('contact_data')[0].services_list[0].list1}>{$t('contact_data')[0].services_list[0].list2}</option>
                    <option value={$t('contact_data')[0].services_list[0].list2}>{$t('contact_data')[0].services_list[0].list3}</option>
                    <option value={$t('contact_data')[0].services_list[0].list3}>{$t('contact_data')[0].services_list[0].list4}</option>
                    <option value={$t('contact_data')[0].services_list[0].list4}>{$t('contact_data')[0].services_list[0].list5}</option>
                    <option value={$t('contact_data')[0].services_list[0].list5}>{$t('contact_data')[0].services_list[0].list6}</option>
                    <option value={$t('contact_data')[0].services_list[0].list6}>{$t('contact_data')[0].services_list[0].list7}</option>
                </select>
            </fieldset>
            <label class="text-white" for="cargo-origin">2. {$t('contact_data')[0].email_list[0].list5}</label>
            <input type="text" name="Origem da carga" id="cargo-origin" placeholder={$t('contact_data')[0].placeholder_list[0].list4} required>
            <label class="text-white" for="cargo-destination">3. {$t('contact_data')[0].email_list[0].list6}</label>
            <input type="text" name="Destino da carga" id="cargo-destination" placeholder={$t('contact_data')[0].placeholder_list[0].list5} required>
            <label class="text-white" for="cargo-description">{$t('contact_data')[0].email_list[0].list7}</label>
            <textarea rows="3" name="Descrição da carga" id="message"
                placeholder=""
                required=""></textarea>
            <fieldset id="fs-frm-selects">
                <label class="text-white" for="importer">{$t('contact_data')[0].email_list[0].list8}</label>
                <select name="Já realizou transporte internacional?" id="importer" required>
                    <option value={$t('contact_data')[0].services_list[0].list1} selected="" disabled="">{$t('contact_data')[0].services_list[0].list1}</option>
                    <option value={$t('contact_data')[0].importer_list[0].list1}>{$t('contact_data')[0].importer_list[0].list2}</option>
                    <option value={$t('contact_data')[0].importer_list[0].list2}>{$t('contact_data')[0].importer_list[0].list3}</option>
                </select>
            </fieldset>
            <input type="hidden" name="_subject" id="email-subject" value="Nova cotação solicitada:">
        </fieldset>
          <input id="submit" class="rounded-full" type="submit" value={$t('contact_data')[0].email_list[0].list9}>
          <iframe name="formSubmitFrame" tile="Holds Submitted form data" rel="nofollow" class="d-none"></iframe>
        </form>
    </div>
</div>

<style>
 #contact {
    background-color: #3D4DA1;
 }

 iframe {
        height: 0px;
        width: 0px;
    }

    #submit {
        border-radius: 25px !important;
    }

 .login-box {
  background: rgba(0,0,0,.5);
  box-sizing: border-box;
  box-shadow: 0 15px 25px rgba(0,0,0,.6);
}

#fs-frm input,
#fs-frm select,
#fs-frm textarea,
#fs-frm fieldset,
#fs-frm optgroup,
#fs-frm label,
#fs-frm #card-element:disabled {
  border: none;
  border-radius: 0;
  display: block;
  width: 100%;
  padding: 0;
  margin: 0;
  -webkit-appearance: none;
  -moz-appearance: none;
}
#fs-frm label,
#fs-frm legend,
#fs-frm ::placeholder {
  font-size: .825rem;
  margin-bottom: .5rem;
  padding-top: .2rem;
  display: flex;
  align-items: baseline;
}

/* border, padding, margin, width */
#fs-frm input,
#fs-frm select,
#fs-frm textarea,
#fs-frm #card-element {
  border: 1px solid rgba(0,0,0,0.2);
  background-color: rgba(255,255,255,0.9);
  padding: .75em 1rem;
  margin-bottom: 1.5rem;
}
#fs-frm input:focus,
#fs-frm select:focus,
#fs-frm textarea:focus {
  background-color: white;
  outline-style: solid;
  outline-width: thin;
  outline-color: gray;
  outline-offset: -1px;
}
#fs-frm [type="text"],
#fs-frm [type="email"] {
  width: 100%;
}
#fs-frm [type="button"],
#fs-frm [type="submit"],
#fs-frm [type="reset"] {
  width: auto;
  cursor: pointer;
  -webkit-appearance: button;
  -moz-appearance: button;
  appearance: button;
}
#fs-frm [type="button"]:focus,
#fs-frm [type="submit"]:focus,
#fs-frm [type="reset"]:focus {
  outline: none;
}
#fs-frm [type="submit"],
#fs-frm [type="reset"] {
  margin-bottom: 0;
}
#fs-frm select {
  text-transform: none;
}

#fs-frm [type="checkbox"] {
  -webkit-appearance: checkbox;
  -moz-appearance: checkbox;
  appearance: checkbox;
  display: inline-block;
  width: auto;
  margin: 0 .5em 0 0 !important;
}

#fs-frm [type="radio"] {
  -webkit-appearance: radio;
  -moz-appearance: radio;
  appearance: radio;
}

/* address, locale */
#fs-frm fieldset.locale input[name="city"],
#fs-frm fieldset.locale select[name="state"],
#fs-frm fieldset.locale input[name="postal-code"] {
  display: inline;
}
#fs-frm fieldset.locale input[name="city"] {
  width: 52%;
}
#fs-frm fieldset.locale select[name="state"],
#fs-frm fieldset.locale input[name="postal-code"] {
  width: 20%;
}
#fs-frm fieldset.locale input[name="city"],
#fs-frm fieldset.locale select[name="state"] {
  margin-right: 3%;
}

</style>