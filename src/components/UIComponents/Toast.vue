<template>
    <v-container class="px-0" fluid>
        <!-- Use these attribute to change style of component -->
        <!-- dismissible, outlined, prominent, shaped, text -->
        <v-alert :border="border" v-bind="$attrs"  :type="type"> {{ value }}</v-alert>
    </v-container>
</template>
<script>
export default {
    name: 'Toast',
    
    props: {
        border: {
            type: String,
            default: 'bottom'
        },
        type: {
            type: String,
            default:'success'
        },
        value: {
            type: String,
            default:'Sample Toast'
        }
    }
};
</script>