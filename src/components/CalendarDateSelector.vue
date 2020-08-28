<template lang="html">
  <div class="calendar-date-selector">
    <!-- eslint-disable-next-line -->
    <span @click="selectPrevious"><</span>
    <span @click="selectCurrent">Current</span>
    <span @click="selectNext">></span>
  </div>
</template>

<script lang="js">
  import dayjs from "dayjs";

  export default {
    name: 'CalendarDateSelector',
    props: {
      currentDate: {
        type: String,
        required: true
      },

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
    methods: {
      selectPrevious() {
        let newSelectedDate = dayjs(this.selectedDate).subtract(1, "month");
        this.$emit("dateSelected", newSelectedDate);
      },

      selectCurrent() {
        let newSelectedDate = dayjs(this.currentDate);
        this.$emit("dateSelected", newSelectedDate);
      },

      selectNext() {
        let newSelectedDate = dayjs(this.selectedDate).add(1, "month");
        this.$emit("dateSelected", newSelectedDate);
      }
    },
    computed: {}
  }


</script>

<style scoped lang="scss">
  .calendar-date-selector {
    display: flex;
    justify-content: space-between;
    width: 80px;
    color: var(--grey-800);
  }

  .calendar-date-selector > * {
    cursor: pointer;
    user-select: none;
  }
</style>
