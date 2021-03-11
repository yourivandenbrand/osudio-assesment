<template>
    <main>
        <site-header :data="data.components.SiteHeader" />
        <hero-text :data="data.components.Herotext" />
        <locations :data="data.components.Locations" :store="store" />
        <site-footer :data="data.components.SiteFooter" />
    </main>
</template>

<script>
import SiteHeader from "~/components/SiteHeader";
import HeroText from "~/components/HeroText";
import Locations from "~/components/Locations";
import SiteFooter from "~/components/SiteFooter";

export default {
    name: "PageStore",
    components: {
        SiteHeader,
        HeroText,
        Locations,
        SiteFooter,
    },

    async asyncData({ params, $axios, app }) {
        const data = await $axios.$get(
            `http://localhost:3000/api/${app.i18n.locale}/get-page-overview.json?store=${params.store}`
        );
        return {
            data,
            store: params.store,
        };
    },
};
</script>