<template>
    <ul class="flex flex-col items-center w-full mt-4 space-y-2">
        <ListItem @remove-todo="$emit('remove-todo',$event)" v-for="todo in todoList" :key="todo.id" :todo="todo"/>
    </ul>
</template>

<script>
import ListItem from './ListItem.vue'
   
export default {
    props:["todoList"],
    
    components:{
        ListItem
    },
    
}
</script>