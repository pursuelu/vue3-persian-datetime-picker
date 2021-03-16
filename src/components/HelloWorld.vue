<template>
  <div>
    <date-picker v-model="date"></date-picker>
  </div>
</template>

<script>
import VuePersianDatetimePicker from '@/components/picker/VuePersianDatetimePicker.vue'
export default {
  setup() {
    const date = ''
    return {
      date
    }
  },
  components: {
    datePicker: VuePersianDatetimePicker
  }
}
</script>
