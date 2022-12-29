<script>
export default {
  name: "HomeView",
  data() {
    return {
      isData: false,
      countries: [],
    };
  },
  mounted() {
    fetch("https://restcountries.com/v2/all")
      .then((response) => response.json())
      .then((data) => {
        this.countries = data;
        this.isData = true;
      });
  },
};
</script>

<template>
  <section>
    <h1 class="text-4xl text-center mb-4">World Countries</h1>
    {{ !isData ? "Loading..." : "" }}
    <div class="grid grid-cols-3 gap-4">
      <div v-for="country in countries" class="border p-4">
        <img :src="country.flag" alt="" class="object-contain h-40 w-40" />
        <div class="flex flex-col gap-y-1">
          <h2 class="text-2xl">Name: {{ country.name }}</h2>
          <h3 class="text-xl">Population: {{ country.population }}</h3>
          <h4 class="text-lg">Capital: {{ country.capital }}</h4>
          <p>Region: {{ country.region }}</p>
          <p>Sub Region: {{ country.subregion }}</p>
        </div>
      </div>
    </div>
  </section>
</template>
