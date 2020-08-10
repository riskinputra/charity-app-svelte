<script>
  import { charities } from "../data/charities";
  import Header from "../components/Header.svelte";
  import Welcome from "../components/Welcome.svelte";
  import CharityList from "../components/CharityList.svelte";
  import Promo from "../components/Promo.svelte";
  import Footer from "../components/Footer.svelte";
  // your script goes here
</script>

<Header />
<Welcome />
<CharityList {charities} />
<Promo />
<Footer />
