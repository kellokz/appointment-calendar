<template>
    <div class=' deleteAll mt-5'>
      <button class="btn btn-danger deleteAllBtn" @click="deleteAll()">Alle Termine löschen</button>
    </div>
</template>

<script>

import { store } from "../store.js";

export default {
    name:'CalendarDeleteAll',

    methods:{
        deleteAll(){
            store.deleteAll();
        },
    }

}

</script>


<style scoped>
.deleteAll{
  display:flex;
  justify-content: center;
}
.deleteAllBtn{
  width:26%;
}
</style>
