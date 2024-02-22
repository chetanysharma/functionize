<template>
  <v-container class="px-0" fluid>
    <component :is="tag" v-bind="$attrs">
      <!-- Slot for content -->
      <slot></slot>
    </component>
  </v-container>
  </template>
  
  <script>
  export default {
    name: 'Heading',
    props: {
      // Define the type of heading (h1, h2, h3, etc.)
      tag: {
        type: String,
        default: 'h1'
      }
    }
  };
  </script>
  