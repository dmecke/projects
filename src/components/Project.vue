<template>
    <v-hover #default="{ hover }">
        <v-card
            outlined
            :href="url"
        >
            <v-img
                :src="require('@/assets/projects/' + image)"
                height="400px"
                class="white--text"
                gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
            >
                <v-card-title class="fill-height align-end">{{ name }}</v-card-title>
            </v-img>
            <v-card-actions>
                <p-state :state="state" />
            </v-card-actions>
        </v-card>
    </v-hover>
</template>

<script>
    import State from "./State";

    export default {
        name: 'p-project',
        components: {
            'p-state': State,
        },
        props: {
            name: {
                type: String,
                required: true,
            },
            image: {
                type: String,
                required: true,
            },
            state: {
                type: String,
                required: true,
            },
            url: {
                type: String,
                required: true,
            },
        },
    }
</script>
