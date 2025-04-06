<script setup>
import { ref } from "vue";
const buttonText = ref("dark mode");

function changeMode() {
    if (buttonText.value == "dark mode") {
        buttonText.value = "light mode";
    } else {
        buttonText.value = "dark mode";
    }

    let root = document.getElementById("root");

    if (root.className == "dark") {
        root.className = "light";
    } else {
        root.className = "dark";
    }
}
</script>

<template>
    <div class="flex flex-col flex-1 items-center justify-center">
        <div class="flex gap-4 mb-12 p-4">
            <div class="p-12 rounded-full bg-white border-1 border-black dark:bg-black dark:border-white"></div>
            <div class="p-12 rounded-full bg-black dark:bg-white"></div>
            <div class="p-12 rounded-full bg-primary dark:bg-secondary"></div>
            <div class="p-12 rounded-full bg-secondary dark:bg-primary"></div>
            <div class="p-12 rounded-full bg-accent"></div>
        </div>

        <button id="dark-mode-button" @click="changeMode">
            {{ buttonText }}
        </button>
    </div>
</template>
