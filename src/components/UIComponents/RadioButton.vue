<template>
    <v-container
    class="px-0"
    fluid
  >
    <v-radio-group v-model="radioValue" v-bind="$attrs">
        
      <v-radio
        v-for="el in data"
        :key="el.id"
        :label="el.label"
        :value="el.value"
      ></v-radio>
    </v-radio-group>
  </v-container>
</template>

<script>
export default {
    name: 'RadioButton',
    data:() => ({
        radioValue:'male'
    }),
    props: {
        data: {
            type: Array,
            default: null
        },
        value: {
            type: String,
            default:''
        }
    }
};
</script>