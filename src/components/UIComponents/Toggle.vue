<template>
    <v-container class="px-0" fluid>
        <v-switch v-bind="$attrs" :label="label"></v-switch>
    </v-container>
</template>

<script>
export default {
    name: 'Toggle',
    props: {
        label: {
            type: String,
            default: null
        }
    }
};
</script>