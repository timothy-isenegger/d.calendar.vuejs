<template lang="html">
  <ol class="day-of-week">
    <li
        v-for="weekday of weekdays"
        :key="weekday">
      {{ weekday }}
    </li>
  </ol>
</template>

<script lang="js">
  const WEEKDAYS = ["Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun"];

  export default  {
    name: 'CalendarWeekdays',
    props: [],
    mounted () {

    },
    data () {
      return {

      }
    },
    methods: {

    },
    computed: {
      weekdays() {
        return WEEKDAYS;
      }
    }
}


</script>

<style scoped lang="scss">
  .day-of-week {
    display: grid;
    grid-template-columns: repeat(7, 1fr);
  }

  .day-of-week > * {
    text-align: right;
    padding-right: 5px;
  }
</style>
