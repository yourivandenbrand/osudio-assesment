<template>
    <footer class="container">
        <div class="row go-all-the-way-to-the-top">
            <div class="col text-center">
                <a href="#">↑ {{ data.backtotopLabel }}</a>
            </div>
        </div>
        <div class="row">
            <div class="col footer text-center">
                <a :href="data.privacyUrl">{{ data.privacyLabel }}</a> - Osudio
            </div>
        </div>
        <b-alert
            v-model="showBottom"
            class="position-fixed fixed-bottom m-0 rounded-0 w-20"
            style="z-index: 2000"
            variant="warning"
            dismissible
        >
            <div class="container">
                <div class="row">
                    <div class="col-12 col-md-8 offset-md-1">
                        {{ gpdr.text }}
                    </div>

                    <div class="col-12 col-md-3 offset-md-0 mt-1">
                        <button
                            class="accept-button p-2 px-4"
                            @click="accept()"
                        >
                            {{ gpdr.button }}
                        </button>
                    </div>
                </div>
            </div>
        </b-alert>
    </footer>
</template>

<script>
export default {
    name: "SiteFooter",
    props: {
        data: {
            required: true,
            type: Object,
        },
    },
    data() {
        return {
            showBottom: false,
            gpdr: "Loading...",
        };
    },
    mounted() {
        if (!this.getGDPR() === true) {
            this.showBottom = true;
        }
    },
    async fetch() {
        this.gpdr = await this.$nuxt.context.$axios.$get(
            `http://localhost:3000/api/${this.$i18n.locale}/get-gpdr.json?store=${this.store}`
        );
    },
    methods: {
        getGDPR() {
            if (process.browser) {
                return localStorage.getItem("GDPR:accepted", true);
            }
        },
        accept() {
            if (process.browser) {
                this.showBottom = false;
                localStorage.setItem("GDPR:accepted", true);
            }
        },
    },
};
</script>

<style>
.accept-button {
    font-size: 16px;
    background: black;
    border-radius: 10px;
    color: white;
    outline: none;
    border: none;
}
.footer {
    padding-top: 30px;
    color: grey;
    font-size: 12px;
}
.footer a,
.footer a:hover {
    color: grey;
    font-size: 12px;
    text-decoration: underline;
}

.go-all-the-way-to-the-top {
    padding-top: 100px;
    padding-bottom: 15px;
}
.go-all-the-way-to-the-top a {
    font-size: 30px;
    font-weight: 400;
    color: #000;
}
.go-all-the-way-to-the-top a span {
    font-size: 16px;
    display: block;
}
.go-all-the-way-to-the-top a:hover {
    text-decoration: none;
}
</style>
