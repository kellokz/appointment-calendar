<template>
<div class="container-fluid">
    <div class="row">
        <div class="col-12">
            <div class="card-group">
                <CalendarTag v-for="day in state.calendarWeekData"
                :key="day.id"
                :day="day"
                 />
            </div>
        </div>
    </div>
</div>
</template>

<script>
import { store } from '../store.js';
import CalendarDay from './CalendarDay.vue';

export default {
    name: 'CalendarWeek',
    data(){
        return {state: store.state}
    },
    components:{
        'CalendarTag':CalendarDay
    }
}

</script>

<style scoped>

</style>