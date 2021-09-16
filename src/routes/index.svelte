<script>
	import Footer from './../lib/Footer.svelte';
	import Contact from './../lib/Contact.svelte';
	import About from './../lib/About.svelte';
	import Solutions from './../lib/Solutions.svelte';
	import Header from './../lib/Header.svelte';
    import Stats from './../lib/Stats.svelte';
	import data from '../data/data';
	import Modal from 'svelte-simple-modal';
	import translations from '../data/translations';
    import { dict, locale, t } from '../data/i18n';
    $: languages = Object.keys(translations);
    $: dict.set(translations);
</script>
<Header />
<Stats stats={data.STATS} />
<Solutions solutions={data.SOLUTIONS} />
<About about={data.ABOUT}/>
<Modal>
	<Contact contact={data.CONTACT}/>
</Modal>
<Footer />

<style>

</style>