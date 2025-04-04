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
        <div class="flex gap-4 mb-12 p-4 bg-black/25 dark:bg-white/25">
            <div class="p-12 rounded-full bg-black dark:bg-black-dark"></div>
            <div class="p-12 rounded-full bg-white dark:bg-white-dark"></div>
            <div
                class="p-12 rounded-full bg-primary dark:bg-primary-dark"
            ></div>
            <div
                class="p-12 rounded-full bg-secondary dark:bg-secondary-dark"
            ></div>
            <div class="p-12 rounded-full bg-accent dark:bg-accent-dark"></div>
        </div>

        <button id="dark-mode-button" @click="changeMode">
            {{ buttonText }}
        </button>
    </div>
</template>
