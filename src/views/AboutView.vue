<script setup lang="ts">
import { ref, onMounted, watch } from 'vue'

// reactive state
const count = ref(0)
const message = ref<string>()

// functions that mutate state and trigger updates
const increment = () => {
  count.value++
}

const addMessage = () => {
  console.log(message.value)
}
watch(message, newMessage => {
  localStorage.setItem('messages', JSON.stringify(newMessage))
  console.log(newMessage)

}, { deep: true })
// lifecycle hooks
onMounted(() => {

  // message.value = localStorage.getItem('message') || ''
})


</script>
<template>
  <div class="about">
    <div class="live-heading" aria-live="polite">
      <h1>This is an about page with count of {{ count }}</h1>
    </div>
    <button class="btn btn-primary" @click="increment">Count</button>
    <div class="activity">
      <form action="POST" @submit.prevent="addMessage">
        <h2>Instructions: Write something about
          RIW</h2>
        <input v-model="message" type="text" placeholder="What do you think about RIW?"
          class="custom-input" name="input-message">
      </form>
      <p class="mt-sm">{{ message }}</p>

      <button class="btn btn-secondary">Add message</button>
    </div>

  </div>
</template>

<style scoped lang="scss">
h1 {
  color: green;
}

.btn {
  margin: 1rem;
  padding: 0.5rem 1rem;
  height: 3rem;
  // margin: auto;
  font-size: 1.5rem;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  filter: grayscale(0);
  transition: filter 250ms ease-in;

  &:hover {
    filter: grayscale(70%);
  }

  &-primary {
    color: #fff;
    background-color: #369;
  }

  &-secondary {
    color: #fff;
    background-color: #3a0763;
  }
}

.custom-input {
  border: 1px solid #333;
  border-radius: 5px;
  width: 20rem;
  height: 3rem;
  font-size: 1.25rem;
  padding-left: 0.75rem;
}

.activity {
  display: flex;
  flex-flow: column wrap;
  justify-items: flex-start;
  align-content: center;

  .btn {
    margin-right: auto;
  }
}

.mb-sm {
  margin-bottom: 1rem;
}

.mt-sm {
  margin-top: 1rem;
}
</style>
