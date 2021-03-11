<template>
    <main>
        <site-header :data="data.components.SiteHeader" />
        <hero-text :data="data.components.Herotext" />
        <booking :data="data.components.Booking" />
        <site-footer :data="data.components.SiteFooter" />
    </main>
</template>

<script>
import SiteHeader from "~/components/SiteHeader";
import HeroText from "~/components/HeroText";
import Booking from "~/components/Booking";
import SiteFooter from "~/components/SiteFooter";

export default {
    name: "PageStore",
    components: {
        SiteHeader,
        HeroText,
        Booking,
        SiteFooter,
    },

    async asyncData({ params, $axios }) {
        // const data = await $axios.$get(`https://run.mocky.io/v3/eb40090e-3d90-4624-b4f9-8c5c393a7a74/?store=${params.store}&location=${params.location}`)
        const data = await $axios.$get(
            `http://localhost:3000/api/get-page-detail.json?store=${params.store}&location=${params.location}`
        );
        return {
            data,
            store: params.store,
            location: params.location,
        };
    },
};
</script>
