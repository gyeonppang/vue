<script setup lang="ts">
</script>

<template>
  <div id="calculator">
    <div class="display">{{ display }}</div>
    <div class="buttons">
      <button v-for="button in buttons" @click="handleClick(button)">
        {{ button }}
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      display: '0',
      buttons: ['C', 'CE', '%', '/', '7', '8', '9', '*', '4', '5', '6', '-', '1', '2', '3', '+', '0', '.', '=']
    }
  },
  methods: {
    handleClick(button) {
      if (button === '=') {
        this.display = eval(this.display)
      } else if (button === 'C') {
        this.display = '0'
      } else if (button === 'CE') {
        this.display = this.display.slice(0, -1)
        if (this.display === '') {
          this.display = '0'
        }
      } else {
        if (this.display === '0') {
          this.display = button
        } else {
          this.display += button
        }
      }
    }
  }
}
</script>

<style>
#calculator {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
}

.display {
  font-size: 48px;
  margin-bottom: 16px;
  padding: 16px;
  border: 1px solid black;
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 16px;
}

button {
  font-size: 24px;
  padding: 16px;
  border: 1px solid rgb(0, 0, 0);
  background-color: white;
  cursor: pointer;
  transition: background-color 0.3s;
}

button:hover {
  background-color: #eee;
}
</style>
