<template>

        <li class="flex items-center w-full p-2 rounded-md" :class="{'bg-lightGreen':todo.done,'bg-myOrange':!todo.done}">
              <div class="flex justify-start items-center flex-1 space-x-2">
                <input  :checked="todo.done" @change="completeTodo(todo)" type="checkbox" class="w-4 h-4">
                <label  class="block wrap">{{ todo.title }}</label>
              </div>
              <button @click="$emit('remove-todo',todo)" class="bg-clifford rounded-md px-4 py-1 text-center text-white">Delete</button>
        </li>

</template>
<script>

    export default {
    props:["todo"],
    inject:["completeTodo"]
    }

    
    
</script>