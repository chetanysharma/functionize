<template>
  <v-app>
    <v-main>
      <UIDashboard/>
    </v-main>
  </v-app>
</template>

<script>
import UIDashboard from '@/components/UIDashboard.vue';

export default {
  name: 'App',

  components: {
    UIDashboard,
  },

  data: () => ({
    //
  }),
};
</script>
