<template>
    <v-container class="px-0" fluid>
        <v-checkbox v-bind="$attrs" :label="label"></v-checkbox>
    </v-container>
</template>

<script>
export default {
    name: 'checkbox',
    props: {
        label: {
            type: String,
            default: null
        }
    }
};
</script>