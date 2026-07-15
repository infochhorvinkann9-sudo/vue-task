<script setup>
import { ref } from 'vue';


const name = ref('Jame Deo');
const status = ref('active');
const tasks = ref([]);
const newTask = ref('')

const toggleStatus = () => {
    if (status.value === 'active') {
        status.value = 'pending'
    } else if (status.value === 'pending') {
        status.value = 'inactive';
    } else {
        status.value = 'active';
    }
};

const addTask = () => {
    if (newTask.value.trim() !== '') {
        tasks.value.push(newTask.value);
        newTask.value = '';
    }
}

const deleteTask = (index) => {
    tasks.value.splice(index, 1)
};
</script>


<template>
    <h1> {{ name }}</h1>
    <p v-if="status === 'active'">user is active</p>
    <p v-else-if="status === 'pending'">user is pending</p>
    <p v-else>user is inactive</p>

    <!-- form for tasks -->
    <form @submit.prevent="addTask">
        <label for="newTask">Add Task</label>
        <input type="text" name="" id="newTask" v-model="newTask">
        <button class="btnAdd" type="submit">Add new</button>
    </form>

    <h3 class="text-head">Add your plan here </h3>
    <li v-for="(task, index) in tasks" :key="task">
        <span>
            <button class="btn-del" @click="deleteTask(index)">Delete</button>
            {{ task }}
        </span>

    </li>
    <button class="chStatus" @click="toggleStatus">Change</button>
</template>

<style>
.text-head {
    color: yellow;
}

.btn-del {
    width: 80px;
    height: 20px;
    border: none;
    border-radius: 5px;
    background-color: red;
}


.btnAdd {
    width: 80px;
    height: 20px;
    border: none;
    border-radius: 5px;
    background-color: greenyellow;
}

.chStatus {
    width: 80px;
    height: 20px;
    border: none;
    border-radius: 5px;
    background-color: skyblue;
}

li {
    list-style: none;
}
</style>