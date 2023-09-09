<template>
    <form class="flex flex-col justify-center items-center w-full space-y-6" @submit.prevent="sendData">
            <div class="flex justify-start items-center w-full space-x-2">
                <input v-model="todo" type="text" name="todo" id="todo" placeholder="Enter a todo..." class="flex-1 border-2 py-2 px-3 border-lightGreen hover:border-darkGreen focus:border-darkGreen focus-within:ring-darkGreen focus-within:border-2 focus-within:ring-inset focus:ring-0 rounded-md ">
                <button class="bg-darkGreen rounded-md px-4 py-2 text-center text-white border-2 border-darkGreen" >Add Todo</button>
            </div>
          </form>
</template>

<script>
export default {
    data(){
        return {
            todo:"",     
        }
        
    },
    methods: {
        sendData(){
            
            this.$emit("add-todo",this.todo)
            this.todo=""
        }
    },
}
</script>