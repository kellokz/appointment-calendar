<template>
    <div class="alert text-center" :class="getEventColor">
         <div  v-if="!event.edit">
            <div>{{event.title}}</div>
            <div>
              <i class="fas fa-edit mr-2" @click="editEvent(day.id, event.title)" style="curser:pointer;"></i>
              <i class="far fa-trash-alt" @click="deleteEvent(day.id, event.title)"  style="curser:pointer;"></i>
            </div>
         </div>
          <div v-if="event.edit">
           <input type="text" class="form-control"
           :placeholder="event.title" v-model="newEventTitle">
           <hr>

            <i class="fas fa-check" @click="updateEvent(day.id, event.title)" style="curser:pointer;" ></i>         
        </div>

     </div>
</template>


<script>
import {store} from '../store.js';
export default {
    name:'CalendarEvent',
    props: ['event','day'],
        data(){
        return{
            newEventTitle:""
        }
    },
    computed:{
        getEventColor(){
            return 'alert-'+ this.event.color;
        }
    },
    methods:{
        editEvent(dayId,eventTitle){
            store.editEvent(dayId,eventTitle);
        },
        updateEvent(day,eventTitle){
            this.newEventTitle=="" ?  this.newEventTitle=eventTitle : "" ;
            store.updateEvent(day, eventTitle, this.newEventTitle);

        },
        deleteEvent(dayId,eventTitle){
            store.deleteEvent(dayId,eventTitle);
        }
    }
    
}
</script>
