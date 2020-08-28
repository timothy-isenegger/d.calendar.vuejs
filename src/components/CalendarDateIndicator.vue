<template lang="html">
  <div class="calendar-date-indicator">{{ selectedMonth }}</div>
</template>

<script lang="js">

  export default {
    name: 'CalendarDateIndicator',
    props: {
      selectedDate: {
        type: Object,
        required: true
      }
    },
    mounted() {

    },
    data() {
      return {}
    },
    methods: {},
    computed: {
      selectedMonth() {
        return this.selectedDate.format('MMMM YYYY');
      }
    }
  }


</script>

<style scoped lang="scss">
  .calendar-date-indicator {
    font-size: 24px;
    font-weight: 600;
    color: var(--grey-00);
  }
</style>
