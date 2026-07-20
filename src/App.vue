<template>

    <!--Call from child to show on parent components -->

    <Cart :title="dynamicTitle" :follower="followered" :isStatus="true" />

</template>

<script setup>
import { watch, reactive, ref } from 'vue'
import Cart from '@/components/ProfileCard.vue';

// const users = reactive({
//     name: "Joe",
//     age: 20
// });

// const nameMessage = ref('')
// const ageMessage = ref('')

// watch(() => users.age, (newAge, oldAge) => {
//     ageMessage.value = `age old changed from ${oldAge} to ${newAge}`
//     console.log(ageMessage.value)
// })

// watch(() => users.name, (newUser, oldUser) => {
//     nameMessage.value = `user old changed from ${oldUser} to ${newUser}`
//     console.log(nameMessage.value)
// })

const dynamicTitle = ref('User Profile')
const followered = ref(110)


</script>