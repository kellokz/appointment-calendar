<template>
  <div id="app ">
   <CalendarWeek/>
   

    <div id="calendar-entry">
     <CalendarEntry/> 
    </div>
      <CalendarDeleteAll/>
  </div>
</template>

<script>
import  CalendarEntry  from './components/CalendarEntry.vue';
import CalendarWeek from './components/CalendarWeek.vue';
import CalendarDeleteAll from './components/CalendarDeleteAll.vue';

export default {
  name: 'App',
  components: {
    CalendarWeek,
    CalendarEntry,
    CalendarDeleteAll
  }
}
</script>
<style scoped>




</style>

