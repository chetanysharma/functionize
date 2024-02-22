<template>
    <v-container class="px-0" fluid>
        <Heading tag="h5" class="heading" style="color:grey; margin-bottom: 10px;">Date Select</Heading>
        <v-date-picker v-bind="$attrs" v-model="value"></v-date-picker>
    </v-container>
</template>
<script>
import Heading from '@/components/UIComponents/Heading.vue';
export default {
  name: 'DatePicker',
  components: {
        Heading
    },
  props: {
    value: {
      type: String,
      default: ''
    }
  }
};
</script>