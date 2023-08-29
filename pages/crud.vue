<template>
    
    <div>
        <h2 class="font-bold text-xl text-center">Todo List</h2>
    </div>

<form @submit.prevent="addtodo">
    <div class="flex justify-center items-center">
        <div class="relative mb-3" data-te-input-wrapper-init> 
            <input
                type="text"
                v-model="newtodocontent"
                class="peer block min-h-[auto] w-full rounded border-0 bg-transparent px-3 py-[0.32rem] leading-[1.6] outline-none transition-all duration-200 ease-linear focus:placeholder:opacity-100 peer-focus:text-primary data-[te-input-state-active]:placeholder:opacity-100 motion-reduce:transition-none dark:text-neutral-200 dark:placeholder:text-neutral-200 dark:peer-focus:text-primary [&:not([data-te-input-placeholder-active])]:placeholder:opacity-0"
                id="exampleFormControlInput1"
                placeholder="Example label" />
            <label
                for="exampleFormControlInput1"
                class="pointer-events-none absolute left-3 top-0 mb-0 max-w-[90%] origin-[0_0] truncate pt-[0.37rem] leading-[1.6] text-neutral-500 transition-all duration-200 ease-out peer-focus:-translate-y-[0.9rem] peer-focus:scale-[0.8] peer-focus:text-primary peer-data-[te-input-state-active]:-translate-y-[0.9rem] peer-data-[te-input-state-active]:scale-[0.8] motion-reduce:transition-none dark:text-neutral-200 dark:peer-focus:text-primary"
                >Example label
            </label>
        </div>
    
        <button
        class="rounded bg-primary px-6 pb-2 pt-2.5 text-xs font-medium uppercase leading-normal text-white shadow-[0_4px_9px_-4px_#3b71ca] transition duration-150 ease-in-out hover:bg-primary-600 hover:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.3),0_4px_18px_0_rgba(59,113,202,0.2)] focus:bg-primary-600 focus:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.3),0_4px_18px_0_rgba(59,113,202,0.2)] focus:outline-none focus:ring-0 active:bg-primary-700 active:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.3),0_4px_18px_0_rgba(59,113,202,0.2)] dark:shadow-[0_4px_9px_-4px_rgba(59,113,202,0.5)] dark:hover:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.2),0_4px_18px_0_rgba(59,113,202,0.1)] dark:focus:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.2),0_4px_18px_0_rgba(59,113,202,0.1)] dark:active:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.2),0_4px_18px_0_rgba(59,113,202,0.1)]">
        Button
        </button>
    </div>
    
</form>

<div v-for="todo in todos" class="flex justify-center">
<div class="w-1/3 mt-10 grid grid-cols-2 border rounded-xl">

    <div class="flex p-10 justify-center rounded-l-lg bg-gray-700" :class="{'bg-green-700' : todo.done}">
    {{ todo.content }}
    </div>

    <div class="items-center justify-center flex">
        <button
            @click="donetodo(todo.id)"
            type="button"
            class="inline-block rounded bg-success px-6 pb-2 pt-2.5 text-xs font-medium uppercase leading-normal text-white shadow-[0_4px_9px_-4px_#14a44d] transition duration-150 ease-in-out hover:bg-success-600 hover:shadow-[0_8px_9px_-4px_rgba(20,164,77,0.3),0_4px_18px_0_rgba(20,164,77,0.2)] focus:bg-success-600 focus:shadow-[0_8px_9px_-4px_rgba(20,164,77,0.3),0_4px_18px_0_rgba(20,164,77,0.2)] focus:outline-none focus:ring-0 active:bg-success-700 active:shadow-[0_8px_9px_-4px_rgba(20,164,77,0.3),0_4px_18px_0_rgba(20,164,77,0.2)] dark:shadow-[0_4px_9px_-4px_rgba(20,164,77,0.5)] dark:hover:shadow-[0_8px_9px_-4px_rgba(20,164,77,0.2),0_4px_18px_0_rgba(20,164,77,0.1)] dark:focus:shadow-[0_8px_9px_-4px_rgba(20,164,77,0.2),0_4px_18px_0_rgba(20,164,77,0.1)] dark:active:shadow-[0_8px_9px_-4px_rgba(20,164,77,0.2),0_4px_18px_0_rgba(20,164,77,0.1)]">
            Done
        </button>
        <button
            @click="deletetodo(todo.id)"
            type="button"
            class="inline-block rounded bg-danger px-6 pb-2 pt-2.5 text-xs font-medium uppercase leading-normal text-white shadow-[0_4px_9px_-4px_#dc4c64] transition duration-150 ease-in-out hover:bg-danger-600 hover:shadow-[0_8px_9px_-4px_rgba(220,76,100,0.3),0_4px_18px_0_rgba(220,76,100,0.2)] focus:bg-danger-600 focus:shadow-[0_8px_9px_-4px_rgba(220,76,100,0.3),0_4px_18px_0_rgba(220,76,100,0.2)] focus:outline-none focus:ring-0 active:bg-danger-700 active:shadow-[0_8px_9px_-4px_rgba(220,76,100,0.3),0_4px_18px_0_rgba(220,76,100,0.2)] dark:shadow-[0_4px_9px_-4px_rgba(220,76,100,0.5)] dark:hover:shadow-[0_8px_9px_-4px_rgba(220,76,100,0.2),0_4px_18px_0_rgba(220,76,100,0.1)] dark:focus:shadow-[0_8px_9px_-4px_rgba(220,76,100,0.2),0_4px_18px_0_rgba(220,76,100,0.1)] dark:active:shadow-[0_8px_9px_-4px_rgba(220,76,100,0.2),0_4px_18px_0_rgba(220,76,100,0.1)]">
            Delete
        </button>
    </div>
    </div>
</div>

    
</template>







<script setup>

import {ref, onMounted} from 'vue'
import {collection, getDocs, onSnapshot, doc, addDoc, deleteDoc, updateDoc, orderBy, query, getFirestore} from "firebase/firestore"; 

const db = getFirestore();


const todolistcollection = collection(db, 'todolist')
const todolistdateorder = query(todolistcollection, orderBy("date", "desc"));


const todos = ref([
    // {
    //     id: 'id1',
    //     content: 'stuff 1',
    //     done: false
    // },
    // {
    //     id: 'id2',
    //     content: 'stuff 2',
    //     done: true
    // }
])

    onSnapshot(todolistdateorder, (querySnapshot) => {
    const fbtodos = []
    querySnapshot.forEach((doc) => {
        const todo = {
            id: doc.id,
            content: doc.data().task,
            done: doc.data().done
        }
        fbtodos.push(todo)
    });
    todos.value=fbtodos
    });


    // onMounted(async() => {
    //     const querySnapshot = await getDocs(collection(db, 'todolist'))
    //     let fbtodos = []
    //     querySnapshot.forEach((doc) => {
    //     console.log(doc.id, " => ", doc.data())
    //     const todo = {
    //         id: doc.id,
    //         content: doc.data().task,
    //         done: doc.data().done
    //     }
    //     fbtodos.push(todo)
    // })
    // todos.value = fbtodos
    // })

//add todo

const newtodocontent = ref ('')

const addtodo = () => {

    addDoc(todolistcollection, {
        task: newtodocontent.value,
        done: false,
        date: Date.now()
});
newtodocontent.value = ''
}

//   const newtodo = {
//     id: uuidv4(),
//     content: newtodocontent.value,
//     done: false
// }
//  todos.value.unshift(newtodo)

const deletetodo = id => {
    deleteDoc(doc(todolistcollection, id))
}

const donetodo = id => {
    const index = todos.value.findIndex(todo => todo.id === id)
    
    updateDoc(doc(todolistcollection, id), {
    done: !todos.value[index].done
});
}

</script>

<style scoped>

</style>