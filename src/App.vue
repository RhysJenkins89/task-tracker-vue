<script setup>
import { ref } from "vue";

const taskTitle = ref("");
const taskDescription = ref("");

function handleSubmit() {
    console.log("Submitting task:", {
        title: taskTitle.value,
        description: taskDescription.value,
    });

    // Reset form fields
    taskTitle.value = "";
    taskDescription.value = "";
}
</script>

<template>
    <h1>Task tracker</h1>
    <form @submit.prevent="handleSubmit">
        <div>
            <label for="title">Task Title:</label>
            <input type="text" id="title" v-model="taskTitle" required />
        </div>
        <div>
            <label for="description">Description:</label>
            <textarea
                id="description"
                v-model="taskDescription"
                rows="4"
            ></textarea>
        </div>
        <button type="submit">Add task</button>
    </form>
</template>

<style scoped></style>
