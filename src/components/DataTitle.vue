<template>
  <div class="text-left">
    <h2 class="text-2x1 font-small">{{ text }}</h2>
    <div class="text-2x1 mt-1 mb-1">
      {{ timestamp }}
    </div>
  </div>
</template>

<script>
import dayjs from 'dayjs';
import { computed } from 'vue';

export default {
  name: 'DataTitle',
  props: ['text', 'dataDate'],
  setup ({ dataDate }) {
    return {
      timestamp: computed(() => dayjs(dataDate)
        .format('MMMM D YYYY, h:mm:ss a'))
    };
  }
};
</script>
