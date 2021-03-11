<template>
    <div class="container">
        <div class="row">
            <div class="col-md">
                <div class="innerpadding">
                    <h2>{{ data.title }}</h2>
                    <ol class="numbered-list">
                        <template v-for="(item, index) in data.steps">
                            <li :key="index">{{ item }}</li>
                        </template>
                    </ol>
                </div>
            </div>
            <div class="col-md">
                <div class="innerpadding-alt">
                    <p>[Bookingsmodule hier]</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "Booking",
    props: {
        data: {
            required: true,
            type: Object,
        },
    },
};
</script>
