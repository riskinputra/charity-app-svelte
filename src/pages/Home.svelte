<script>
  import Header from "../components/Header.svelte";
  import Welcome from "../components/Welcome.svelte";
  import CharityList from "../components/CharityList.svelte";
  import Promo from "../components/Promo.svelte";
  import Footer from "../components/Footer.svelte";
  import Loader from "../components/Loader.svelte";
  // your script goes here

  let title = "Charity";
  let data = getData();

  async function getData() {
    const res = await fetch("https://charity-api-bwa.herokuapp.com/charities");
    const data = await res.json();

    if (res.ok) {
      return data;
    } else {
      throw new Error(data);
    }
  }
</script>

<Header />
<Welcome />
{#await data}
  <Loader />
  <!-- #preloader -->
{:then charities}
  <CharityList {charities} />
{/await}
<Promo />
<Footer />
