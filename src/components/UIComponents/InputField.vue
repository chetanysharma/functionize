<template>
    <v-container class="px-0" fluid>
        <Heading tag="h5" class="heading" style="color:grey; margin-bottom: 10px;">
            {{ label }}
        </Heading>
        <v-text-field v-if="type != 'textarea'" v-bind="$attrs" v-model="value" :placeholder="placeholder" :type="type"
            :disabled="disabled" :required="required" :counter="counter" :rules="rules" :hint="hint"></v-text-field>

        <v-textarea v-else v-bind="$attrs" v-model="value" :hint="hint" :placeholder="placeholder"></v-textarea>

    </v-container>
</template>
  
<script>
import Heading from '@/components/UIComponents/Heading.vue';
export default {
    name: 'InputField',
    components: {
        Heading
    },
    props: {
        value: {
            type: [String, Number],
            default: ''
        },
        label: {
            type: String,
            default: 'Label'
        },
        placeholder: {
            type: String,
            default: 'Placeholder'
        },
        type: {
            type: String,
            default: 'text'
        },
        disabled: {
            type: Boolean,
            default: false
        },
        required: {
            type: Boolean,
            default: false
        },
        outlined: {
            type: Boolean,
            default: false
        },
        counter: {
            type: [Boolean, Number],
            default: false
        },
        rules: {
            type: Array,
            default: () => []
        },
        hint: {
            type: String,
            default: ''
        }
    }
};
</script>
  