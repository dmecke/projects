<template>
    <v-chip :color="color" :dark="dark" small>
        <v-icon left small>{{ icon }}</v-icon>
        {{ state }}
    </v-chip>
</template>

<script>
    export default {
        name: 'p-state',
        props: {
            state: {
                type: String,
                required: true,
            },
        },
        computed: {
            color() {
                switch (this.state) {
                    case 'production':
                        return 'green';

                    case 'alpha':
                        return 'blue';

                    case 'prototype':
                        return 'amber';
                }

                return '';
            },
            dark() {
                switch (this.state) {
                    case 'production':
                    case 'alpha':
                        return true;
                }
                return false;
            },
            icon() {
                switch (this.state) {
                    case 'production':
                        return 'mdi-flag';

                    case 'alpha':
                        return 'mdi-content-cut';

                    case 'prototype':
                        return 'mdi-wrench';
                }

                return '';
            },
        }
    }
</script>
