<script setup>

// This child components

const props = defineProps({
    title: String,
    follower: Number,
    isStatus: Boolean
})

console.log(props.title)
</script>

<template>
    <h1 class="cl">{{ title }}</h1> <br>
    <p yl>Follower: {{ follower }}</p> <br>
    <p gre>Status: {{ isStatus ? 'Online' : 'Offline' }}</p>
</template>

<style>
.cl {
    color: aqua;
}
</style>