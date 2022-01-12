<script>
import Footer from './../lib/Footer.svelte';
import Contact from './../lib/Contact.svelte';
import About from './../lib/About.svelte';
import Values from './../lib/Values.svelte';
import Services from '../lib/Services.svelte';
import Header from './../lib/Header.svelte';
import Stats from './../lib/Stats.svelte';
import Whatsapp from '$lib/Whatsapp.svelte';
import data from '../data/data';
import Modal from 'svelte-simple-modal';
import Map from './../lib/Map.svelte';
import Rotative from './../lib/Rotative.svelte';
import translations from '../data/translations';
import {
    dict,
    locale,
    t
} from '../data/i18n';
$: languages = Object.keys(translations);
$: dict.set(translations);
</script>

<Header />
<Whatsapp />
<Stats stats={data.STATS} />
<Rotative />
<Services services={data.SERVICES} />
<About about={data.ABOUT}/>
<Values about={data.ABOUT} />
<Modal>
    <Contact contact={data.CONTACT}/>
</Modal>
<Map />
<Footer />

<style>

</style>
