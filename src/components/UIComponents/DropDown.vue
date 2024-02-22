<template>
    <v-container class="px-0" fluid>
        <!-- Use these attribute to chnage style of dropdown -->
        <!-- auto-select-first, chips, clearable, deletable-chips, multiple, rounded, small-chips, solo -->
        <Heading tag="h5" class="heading" style="color:grey; margin-bottom: 10px;">DropDown with Search </Heading>
        <v-autocomplete v-bind="$attrs" :items="items" item-text='name' item-value="id"></v-autocomplete>
    </v-container>
</template>
<script>
import Heading from '@/components/UIComponents/Heading.vue';
export default {
    name: 'DropDown',
    components: {
        Heading
    },
    props: {
        items: {
            type: Array,
            default: null
        }
    }
};
</script>