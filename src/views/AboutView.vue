<script setup lang="ts">
import { ref, onMounted } from 'vue'

// reactive state
const count = ref(0)
const message = ref<string>()

// functions that mutate state and trigger updates
function increment() {
  count.value++
}

// lifecycle hooks
onMounted(() => {
  // localStorage.setItem('InputMessage', )
})
</script>
<template>
  <div class="about">
    <h1>This is an about page with count of {{ count }}</h1>
    <button class="btn btn-primary" @click="increment">Count</button>
    <p class="mb-sm"><span class="instructions">Instructions:</span> Write something about
      RIW</p>
    <input v-model="message" placeholder="What do you think about RIW?"
      class="custom-input" name="input-message">
    <p class="mt-sm">{{ message }}</p>
  </div>
</template>

<style scoped lang="scss">
h1 {
  color: green;
}

.btn {
  margin: 1rem;
  padding: 0.5rem 1rem;
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

.mb-sm {
  margin-bottom: 1rem;
}

.mt-sm {
  margin-top: 1rem;
}
</style>
