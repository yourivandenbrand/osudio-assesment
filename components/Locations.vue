<template>
    <div class="container">
        <div class="row">
            <div class="col text-center">
                <h2>{{ data.title }}</h2>
            </div>
        </div>
        <div class="row indexpadding">
            <p v-if="$fetchState.pending">{{ data.pending }}</p>
            <p v-else-if="$fetchState.error">{{ data.error }}</p>
            <template v-for="location in locations" v-else>
                <div class="col-md-4 text-center" :key="location.id">
                    <NuxtLink :to="`${store}/${location.id}`" class="button">
                        {{ location.title }}
                        <span>{{ location.subtitle }}</span>
                    </NuxtLink>
                </div>
            </template>
        </div>
    </div>
</template>

<script>
export default {
    name: "Locations",
    props: {
        data: {
            required: true,
            type: Object,
        },

        store: {
            required: true,
            type: String,
        },
    },

    data() {
        return {
            locations: [],
        };
    },

    async fetch() {
        this.locations = await this.$nuxt.context.$axios.$get(
            `http://localhost:3000/api/${this.$i18n.locale}/get-locations.json?store=${this.store}`
        );
    },
};
</script>
