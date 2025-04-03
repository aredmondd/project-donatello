<script setup>
import { ref } from "vue";
import { invoke } from "@tauri-apps/api/core";

const greetMsg = ref("");
const name = ref("");

async function greet() {
    // Learn more about Tauri commands at https://tauri.app/develop/calling-rust/
    greetMsg.value = await invoke("greet", { name: name.value });
}
</script>

<template>
    <div class="flex flex-col flex-1 items-center justify-center">
        <h1>hello there</h1>
    </div>
</template>

<!--         <h1>Welcome to Tauri + Vue</h1>

<form class="row" @submit.prevent="greet">
    <input
        id="greet-input"
        v-model="name"
        placeholder="Enter a name..."
    />
    <button type="submit">Greet</button>
</form>
<p>{{ greetMsg }}</p> -->
